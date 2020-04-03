    #Code on logging light data with particle device to ThingSpeak

    int photoresistor = A0;
    int led = A5;


    void setup() {

        pinMode(led, OUTPUT);
        pinMode(photoresistor, INPUT);
    }

    void loop() {
        digitalWrite(led, HIGH);
        String light = String(analogRead(photoresistor));
        Particle.publish("light", light, PRIVATE);
        delay(500);

        digitalWrite(led, LOW);
        delay(500);
    }
