# section3.1判断文件是否拷贝正确

需求：远程拷贝文件之后，在文件拷贝的目录判断文件是否拷贝成功。

scp lwang@192.168.1.159:~/bm1682_server/data/*.tgz /mnt/data
sync

echo "QA_PASS"


思路：使用md5sum命令获取正确文件的md5码，获取拷贝之后的文件的md5码和正确的文件对比。


rootfs_md5=`md5sum rootfs.tgz | cut -d " " -f 1`
system_md5=`md5sum system.tgz | cut -d " " -f 1`
test_md5=`md5sum test.tgz | cut -d " " -f 1`

judge_rootfs="af64f53e2c05de4cebb64dc34a262897" 
judge_system="93bd37b760425f21cf704c9f01efedfc"
judge_test="1bdafcdfd424c370f4a70a81cb4d5252"

if [ ${rootfs_md5} = ${judge_rootfs} ]&&[ ${system_md5} = ${judge_system} ]&&[ ${test_md5} = ${judge_test} ]
    then
	echo "QA_PASS"
	echo "QA_PASS"
	echo "QA_PASS"
fi




