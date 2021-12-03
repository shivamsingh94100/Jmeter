# Database Connection 
sudo PGPASSWORD=QNeQZg3u  psql -h fareye-qa-load-9-6.cibtmskbddcw.us-west-2.rds.amazonaws.com -Ufareye -d postgres


#QA Server
  ssh-add qaservernew.pem 
  chmod 600 qaservernew.pem 
  ssh -i qaservernew.pem ubuntu@qa.fareye.co


#Jmeter Server
  ssh-add jmeter_new.pem
  ./jmeter_serv.sh 
