- ## how to create a form page and direct the form data to an api endpoint
  - create html web page with form & form attrbs
    - ```html 
            <!DOCTYPE html>
            <html>
            <head>
                <title>zero_fox_layer</title>
            </head>
            <body>
                <form method="post" action="http://127.0.0.1:5000/cisco/ios/send_device_config">
                    <table>
                        <tr>
                            <td>
                                New Device Hostname :
                            </td>
                            <td>
                                <input type="text" placeholder="HQ_CSW-01" name="new_dev_hostname">
                            </td>
                        </tr>
                        <tr>
                            
                        </tr>
                        <tr>
                            <td>
                                <input type="submit" name="">
                            </td>
                        </tr>
                    </table>
                </form>
            </body>
            </html>
      ```
  - a sample of a flask app source code to receive the form data
    - ```python
        from flask import Flask
        from flask_restful import Resource, Api

        app = Flask(__name__)
        api = Api(app)
        
        class GetDeviceConfig(Resource):
        def get(self):
          return {'message': 'place device config here'}

        # the "request.form['new_dev_hostname']" method will retreive the value for the key "new_dev_hostname" from the form data
        class SendDeviceConfig(Resource):
          def post(self):
            form_data = request.form['new_dev_hostname']
            return {'message sent': form_data}


        api.add_resource(GetDeviceConfig, '/cisco/ios/get_device_config')
        api.add_resource(SendDeviceConfig, '/cisco/ios/send_device_config')
      ```
---
---

