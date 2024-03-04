class VSOMEIPThread : public QObject
{
    Q_OBJECT



public:
    VSOMEIPQtClient *m_vsomeipClient = nullptr;
    VSOMEIPThread(VSOMEIPQtClient *vs, QObject *parent = nullptr) : QObject(parent) {
        m_vsomeipClient = vs;
    }



public slots:
    void startVSOMEIP()
    {
        //VSOMEIPQtClient vsomeipClient(true);
        m_vsomeipClient->init();
        m_vsomeipClient->start();
        QCoreApplication::exec();
    }
};


in main now we call the instance by:
   view.rootContext()->setContextProperty("vsomeipClient", (vsomeipThread.m_vsomeipClient));    ==> this will make it used in qml 