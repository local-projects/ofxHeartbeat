# ofxHeartbeat

This is an OpenFrameworks addon designed to send out heartbeats over OSC UDP to the performance monitoring app [ampm](http://github.com/local-projects/ampm). A heartbeat is a UDP message containing the string `'heart'`. By default, ampm accepts these heartbeat messages on port `3002`. An example follows:

_ofApp.h_
```c++
#include "ofxHeartbeat.h"

class ofApp : public ofBaseApp {
public:

  ofxHeartbeat hb;
  
}
```

_ofApp.cpp_
```c++
void ofApp::setup() {

  hb.setup('127.0.0.1', 'my-app-name', 3002);
  hb.start();
  hb.resetCountdown();

}

void ofApp::update() {

  hb.update(ofGetLastFrameTime());

}

```

