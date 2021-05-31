# portenta_lora_tnn  

In the first_config branch, you will find code to help connect to the TTN (the things network) network.  you can follow the instructions here : https://www.arduino.cc/pro/tutorials/portenta-h7/vs-ard-ttn to create a ttn application and get the code for the next proces.

The main branch will contains some simple code to send a message to TTN with the "hello world" message.  You will also need a arduino_secrets.h file with 2 lines.  Fill in the codes from the process (first_config) above:

#define SECRET_APP_EUI "code goes here"
#define SECRET_APP_KEY "code goes here"

The upload code to process the message within TTN is below: 

function decodeUplink(input) {
  return {
    data: {
      message: String.fromCharCode.apply(null, input.bytes)
    },
    warnings: [],
    errors: []
  };
}