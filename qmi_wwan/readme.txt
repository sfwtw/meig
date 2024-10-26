1. 此版qmi_wwan.c 在linux pc 的3.10,3.18,4.2,4.15,5.4 内核上验证通过。拨号方式为meig-cm+qmi_wwan的驱动。

    验证模块为slm730，slm750，srm815.
2. qmi_wwan驱动和gobinet驱动类似。加载后，dev下会有cdc-wdm0的节点。有这个节点后，上位机可以通过它发送qmi。

3.  qmi_wwan.c 依赖usbnet,和cdc-wdm。

4.  linux pc 上验证如下，

     4.1 make 生成qmi_wwan.ko
	 4.2 modprobe usbnet
	 4.3 modprobe cdc-wdm
	 4.4 insmod qmi_wwan.ko
	 
	 4.5 执行meig-cm 
	 
5.  此版本为初始版本。目前qmi_wwan.c驱动还没有纳入测试，也没有集成到ril上。后续会纳入测试，并根据测试反馈情况解决可能是驱动导致的bug。
		 