# Database Connection 
sudo PGPASSWORD=QNeQZg3u  psql -h fareye-qa-load-9-6.cibtmskbddcw.us-west-2.rds.amazonaws.com -Ufareye -d postgres


#QA Server
  ssh-add qaservernew.pem 
  chmod 600 qaservernew.pem 
  ssh -i qaservernew.pem ubuntu@qa.fareye.co


#Jmeter Server
  ssh-add jmeter_new.pem
  ./jmeter_serv.sh 



##Runsheet
  ldr -f Runsheet_generator.java 
  cat runsheet.csv |grep "BANKPASS"|head -50> runnew.csv 
  cat runsheet.csv |grep "BANKFAIL"|head -50>> runnew.csv
  cp runnew.csv ./gendata/runsheet.csv
  ./runsheet.sh 
  ./gen_managerData.sh
  ./manager.sh
