A.  <br />

#!/bin/bash  <br />

######################################################  <br />
Help()  <br />
{ <br />
        # Display Help  <br />
        echo "Syntax: scriptTemplate [--all|--target]"  <br />
        echo "options:"  <br />
        echo "--all Displays the IP addresses and symbolic names of all hosts in the current subnet."  <br />
        echo "--target Displays a list of open system TCP ports." <br />
} <br />
 <br />
All()   <br />
{   <br />
        # Display --all   <br />
        result=`arp -a | awk '{print $1; print $2}'`   <br />
        echo $result  <br />
}  <br />
 <br />
Target() <br />  
{  <br />
        # Display --target  <br />  
        printf "%s\n" `ss -tulpn | grep "tcp" | awk '{print $5}' | awk -F: '{print $2}'`  <br />    
        # echo $target      <br />
}       <br />
 <br />
case $1 in  <br />       
        --all)     <br />    
        All          <br />
        ;;           <br />
        --target)           <br /> 
        Target            <br />
        ;;              <br />
        *)               <br />
        Help                <br />
        ;;                 <br />
esac                 <br />
 <br />
Script works properly:  <br />                
 ![A](A.png)                  <br />
 <br />
B.  <br />
 <br />
#!/bin/bash  <br />
 <br />
Help() <br />
{ <br />
        # Display Help  <br />
        echo "Syntax: scriptName [--rip|--rp|--nr|--nep|--rt|--bot]"  <br />
        echo "options:"  <br />
        echo " --rip   ip-address with most requests"  <br />
        echo " --rp    most requested  page"  <br />
        echo " --nr    number of requests from each ip-address "  <br />
        echo " --nep   requests for  non-existent page "  <br />
        echo " --rt    most requested time "  <br />
        echo " --bot   search-bot requests "  <br />
} <br />
 <br />
rip()  <br />
{ <br />
        #  Display --rip ip-address with most requests <br />
        cat logex.txt | awk '{print $1}' | sort -n |  uniq -c | sort -nr | awk 'NR==1{print $2}' <br />
        <br />
} <br />
<br />
rp() <br />
{ <br />
        #  Display --rp  most requested  page <br />
        cat logex.txt | awk '{print $7}' | sort -n |  uniq -c | sort -nr | awk 'NR==1{print $2}' <br />
} <br />
 <br />
nr() <br />
{ <br />
        #  Display --nr   number of requests from each ip-address <br />
<br />
        cat logex.txt | awk '{print $1}' | sort -n |  uniq -c | sort -nr <br />
<br />
} <br />
<br />
nep() <br />
{ <br />
        #  Display --nep requests for  non-existent page <br />
        awk '{ if($9 != 200) { print $1 } }' logex.txt | sort | uniq -c | sort -nr <br />
<br />
} <br />
<br />
rt() <br />
{ <br />
        #  Display --rt most requested time <br />
        cat logex.txt | awk '{print $4}' | sort -n |  uniq -c | sort -nr |  awk 'NR==1{print $2}' <br />
<br />
} <br />
<br />
bot() <br />
{ <br />
        #  Display --bot search-bot requests <br />
        grep "bot" -F logex.txt | awk '{ print $14 " + " $1 }' | grep "[b,B]ot" | sort | uniq <br />
<br />
} <br />
<br />
<br />
<br />
case $1 in <br />
        --rip) <br />
        rip <br />
        ;; <br />
        --rp) <br />
        rp <br />
        ;; <br />
        --nr) <br />
        nr <br />
        ;; <br />
        --nep) <br />
        nep <br />
        ;; <br />
        --rt) <br />
        rt <br />
        ;; <br />
        --bot) <br />
        bot <br />
        ;; <br />
        --h)    Help <br />
esac <br />
<br />
Script works properly: <br />                 
 ![B](B.png) <br />
<br />
C. <br />
#!/bin/bash <br />
<br />
logfile="/home/veron/sync.log" <br />
filename_added=`diff -q /home/veron/Myscripts/ /home/veron/Myscriptsync/ | awk '/Only in \/home\/veron\/Myscripts\// {print $4}'` <br />
filename_deleted=`diff -q /home/veron/Myscripts/ /home/veron/Myscriptsync/ | awk '/Only in \/home\/veron\/Myscriptsync\// {print $4}'` <br />
if [[ -n $filename_deleted ]] <br />
then <br />
    result="[INFO] " <br />
    result+=`date "+%D %R"` <br />
    result+=" - " <br />
    result+=$filename_deleted <br />
    result+=" DELETED" <br />
    # Put here a method of file deletion <br />
    echo $result >> $logfile <br />
fi <br />
if [[ -n $filename_added ]] <br />
then <br />
    result="[INFO] " <br />
    result+=`date "+%D %R"` <br />
    result+=" - " <br />
    result+=$filename_added <br />
    result+=" ADDED" <br />
    # Put here a method of file addition <br />
    echo $result >> $logfile <br />
fi <br />
<br />
rsync -au --delete "/home/veron/Myscripts/" "/home/veron/Myscriptsync/" <br />
<br />
Script works properly:                <br /> 
 ![C](C.jpg) <br />


