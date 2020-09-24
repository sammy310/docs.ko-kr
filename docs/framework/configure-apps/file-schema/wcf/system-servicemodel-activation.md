---
title: <system.serviceModel.activation>
ms.date: 03/30/2017
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
ms.openlocfilehash: cbb12ce84f53f55f7d5b2dabd449a116969dc9b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157137"
---
# \<system.serviceModel.activation>

<span data-ttu-id="fb72e-102">이 구성 섹션은 SMSvcHost.exe 도구에 대한 구성 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb72e-102">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="fb72e-103">해당 구성 요소는 SMSvcHost.exe.config 파일에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb72e-103">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="fb72e-104">특히 여기에는 구성해야 하는 모든 시스템 수준의 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb72e-104">Specifically, it includes all machine-wide settings that must be configured.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel.activation>**  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="fb72e-105">샘플 구성 파일</span><span class="sxs-lookup"><span data-stu-id="fb72e-105">Sample Configuration File</span></span>  

 <span data-ttu-id="fb72e-106">다음은 수신기 프로세스 SMSvcHost.exe가 사용하는 샘플 구성 파일(SMSvcHost.exe.config)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb72e-106">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
```xml  
<configuration>
  <runtime>
    <gcConcurrent enabled="false" />
  </runtime>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="10"
             maxPendingAccepts="2"
             maxPendingConnections="100"
             receiveTimeout="00:00:10"
             teredoEnabled="false">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
    <net.pipe maxConnectionsPendingDispatch="100"
              maxPendingAccepts="2"
              receiveTimeout="00:00:10">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
    <diagnostics performanceCountersEnabled="true" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="fb72e-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb72e-107">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration>
