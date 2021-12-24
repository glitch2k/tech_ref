- ## import statement to use flask-RESTful
  - install flask-RESTful with pip(3)
    - ``` 
          pip3 install flask-RESTful
      ```
  - import statement
    - ```python 
        from flask import Flask
        from flask_restful import Resource, Api 
      ```
---
---
- ## create a class from the Flash super-class
  - ```python 
      from flask import Flask
      from flask_restful import Resource, Api

      app = Flask(__name__)
      api = Api(app)

      [enter app code here]

      if __name__ == '__main__':
        app.run() 
    ```
---
---
- ## create a **GET** endpoint
    ```python
      from flask import Flask
      from flask_restful import Resource, Api

      app = Flask(__name__)
      api = Api(app)
      
      class HelloWorld(Resource):
      def get(self):
          return {'hello': 'world'}

      api.add_resource(HelloWorld, '/')
      
      
      if __name__ == '__main__':
        app.run() 
    ```
---
---
- ## how to get the data from the body of a **POST** request
    ```python
      from flask import Flask
      from flask_restful import Resource, Api

      app = Flask(__name__)
      api = Api(app)
      
      class GetDeviceConfig(Resource):
      def get(self):
        return {'message': 'place device config here'}

      # the "request.get_json()" method will retreive the data from the body
      #...of the request sent by the client
      class SendDeviceConfig(Resource):
          def put(self):
              data = request.get_json()
              return {'message sent': data['config']}

      api.add_resource(GetDeviceConfig, '/cisco/ios/get_device_config')
      api.add_resource(SendDeviceConfig, '/cisco/ios/send_device_config')
    ```
---
---



