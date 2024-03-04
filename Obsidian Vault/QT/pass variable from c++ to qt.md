### in c++:

    Q_PROPERTY(int receivedInt READ getReceivedInt NOTIFY receivedIntChanged)

    Q_INVOKABLE int getReceivedInt() const { return receivedInt; }
Q_INVOKABLE  makes it accessile in qml 


       QMutexLocker locker(&mutex_);
            if (receivedInt != newReceivedInt) {
                receivedInt = newReceivedInt;
                emit receivedIntChanged();
            }


#### in qml:
   Connections {
        target: vsomeipClient
        onReceivedIntChanged: {
            console.log("Received Int Changeddddddddddddddddddddd:", vsomeipClient.receivedInt);
        }
    }

vsomeip client is set a property to be shared in qml in  [[Instance when thread]]