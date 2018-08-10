# To populate the Libraries folder, follow these instructions:

https://courses.edx.org/courses/course-v1:AWS+OTP-AWSD1+1T2018/courseware/840f80af07e54f41bedfce70a7a0f4c5/5e11294677ed48f3bd8bcd9ba3a6e4a2/3?activate_block_id=block-v1%3AAWS%2BOTP-AWSD1%2B1T2018%2Btype%40vertical%2Bblock%40cdc054ad36a84f3fac5133e7a68735cf



10. Package the libraries needed for the AWS Lambda function and update the AWS Lambda function.

In this section, you will package the AWS Lambda function along with the MySQL connector libraries AWS Lambda needs to execute successfully.

    Type the command below in your AWS Cloud9 terminal to make sure you are in the ~/environment directory of your AWS Cloud9 instance.

    cd ~/environment
    In your AWS Cloud9 environment, create a folder called libraries by typing the command below.

    mkdir libraries
    To include the SQL connector libraries, type the command below.

    pip-3.6 install 'mysql_connector_python<8.1' -t libraries
    Change your working directory to the Libraries folder by typing the command below.

    cd libraries/
    Create a .zip file named lambda.zip and zip the MySql connector libraries by typing the command below.

    zip -r ~/environment/lambda.zip *
    To include the AWS Lambda function code files in the lambda.zip file, change the directory to the exercise folder by typing the command below.

    cd ~/environment/exercise-lambda/LambdaImageLabels/
    Zip the AWS Lambda function code files in the lambda.zip file by typing the command below.

    zip ~/environment/lambda.zip *.py

    The lambda.zip file is now ready with the code and its dependency libraries.
    Change your working directory to the ~/environment folder by typing the command below.

    cd ~/environment
    Using the AWS CLI command below, update the AWS Lambda function you created in an earlier section of this exercise with the function code.

    aws lambda update-function-code --function-name labels-lambda --zip-file fileb://lambda.zip

    Upon executing the AWS CLI command, you should see a JSON output with the information of the AWS Lambda function. This means that the function has been successfully updated with the Python code and libraries.



