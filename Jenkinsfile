pipeline{
    agent any

    stages{
        stage("build"){
           steps{
                
               sh  """
                    sudo ssh -i /var/lib/jenkins/jk.pem -t -o StrictHostKeyChecking=no  << EOF
                    cd /var
                    sudo mkdir html
                    sudo chown -R jenkins:jenkins html/
                    cd /var/html
                    sudo git clone https://github.com/theoafactor/bitblog.git . 
                    sudo docker build -t bitblog:1 .
                    <<EOF
                    """
               
            
               


           }
            
        }


        stage("get"){
            steps{
                echo "get stage"
            }

        }


        stage("production"){

            steps{
                echo "Production"
            }
        }



    }


}