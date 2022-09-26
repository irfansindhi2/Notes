Bitbucket: https://bitbucket.nsf.gov/projects/MYN/repos/referencedataservice/browse?at=refs%2Fheads%2FMAM-11232-springboot-2.7.3

Jenkins dashboard: https://jenkins.nsf.gov/job/DIS/job/MyNSF/

Current quarter status page: https://confluence.nsf.gov/display/MYNSF/MyNSF+Services+-+EOL+Updates+for+Q3-Q4%272022

How to build , deploy and debug in MyNSF Cloud: https://confluence.nsf.gov/display/MYNSF/How+to+build+%2C+deploy+and+debug+in+MyNSF+Cloud

Reference Data Service SonarQube: https://sonarqube.nsf.gov/dashboard?id=gov.nsf.services.reference%3Areference

prod kubernetes: https://k8sdashboard.aws-prod.nsf.gov/#/search?namespace=nsf-dis-apps-prod&q=projectreport

dev kubernetes: https://k8sdashboard.aws-dev.nsf.gov/

aws sign-in: https://signin.aws.amazon.com/saml

query: fields @timestamp, @message, @log
| filter ispresent(kubernetes.pod_name) and kubernetes.pod_name like /projectreport-service-7bb6b6b848/ | filter kubernetes.container_image not like /nginx_tls/ and kubernetes.namespace_name like /nsf-dis-apps-prod/ and @message like /exception/
| limit 10
| fields tomillis(@timestamp) as millis
| filter millis > 1663308000000 and millis < 1663387200000

Migrate MyNSF Spring application to Springboot: https://confluence.nsf.gov/pages/viewpage.action?spaceKey=MYNSF&title=Migrate+MyNSF+Spring+application+to+Springboot

Helm project repos: https://bitbucket.nsf.gov/projects/HELM/repos/