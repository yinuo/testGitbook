# section3.2判断是否挂载成功

需求：shell脚本程序里面怎么判断mount是否挂载成功？


思路：shell脚本里面程序执行成功之后状态码会返回0



mount -t ext4 /dev/mmcblk0p3 /mnt/rootfs/

rootfs_state="$?"

sync

if [ $rootfs_state -eq 0 ]

	then

		echo "QA_PASS"

fi

