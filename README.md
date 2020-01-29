kubeless function deploy hello --runtime python3.7 --from-file test.py --handler test.handler

kubeless function ls hello

kubeless function call hello --data 'Hello world!'

kubeless function update hello -f test.py

kubeless trigger http create hello --function-name hello

kubeless trigger http create hello --function-name hello --hostname localhost --gateway traefik

kubeless trigger kafka create test --function-selector created-by=kubeless,function=hello --trigger-topic hello-topic

kubeless topic publish --topic hello-topic --data "Hello World!"
