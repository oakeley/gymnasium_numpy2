# gymnasium_numpy2
Patch of gymnasium

It's quite annoying that torchRL doesn't work with gymnasium v1 but gymnasium v0.29.1 doesn't work with numpy2

So I made this patch

wget https://github.com/Farama-Foundation/Gymnasium/archive/refs/tags/v0.29.1.tar.gz

tar -zxf v0.29.1.tar.gz

cd Gymnasium-0.29.1/

find . | grep py$ | awk '{A=substr($0,1,length($0)-3); print "mv "$0" "A".orig; cat "$0" | sed '"'"'s/np.float_/np.float64/g'"'"' > "$0}' > patch.sh

bash patch.sh

pip install -e ".[classic_control]"


https://www.swisstransfer.com/d/7f7072ee-ba69-499d-90e7-4f1888e4437b
