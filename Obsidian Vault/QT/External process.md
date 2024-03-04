 1-  First declare a class and set the wanted  command 
`public:
 ``   ProcessStarter(QObject *parent = 0) : QProcess(parent) {
   ``     setProcessChannelMode(QProcess::MergedChannels);
    ``}
    `virtual ~ProcessStarter() = default;
    `Q_INVOKABLE void startMpv(const QString &file, const QStringList &additionalArgs)

    { QStringList args;
        args << "--untimed";
        args << file;
        args << additionalArgs;

        QProcess::start("mpv", args);
    }
    Q_INVOKABLE void stopMpv()
    {
        if (state() == QProcess::Running) {
            terminate();

            if (!waitForFinished(1000)) {
                kill();
                waitForFinished();
            }
            QProcess::startDetached("xdotool", QStringList() << "search" << "--onlyvisible" << "--class" << "mpv" << "windowkill");
        }
    }
    Q_INVOKABLE QByteArray readAll() {
        return QProcess::readAll();
    }
``};

2-Register the type in main :

    qmlRegisterType<ProcessStarter>("Process", 1, 0, "ProcessStarter");
3-call and import it in qml :

 `import Process 1.0
