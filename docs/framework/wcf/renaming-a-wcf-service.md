---
description: '자세한 정보: WCF 서비스 이름 바꾸기'
title: WCF 서비스 이름 바꾸기
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 8d75e43f4bda97e8ee6de34b039eb1236d6c4a6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779168"
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="e0e90-103">WCF 서비스 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="e0e90-103">Renaming a WCF Service</span></span>

<span data-ttu-id="e0e90-104">이 항목에서는 WCF (Windows Communication Foundation) 서비스의 이름을 바꾸는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-104">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="e0e90-105">WCF 서비스 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="e0e90-105">Renaming a WCF Service</span></span>  

 <span data-ttu-id="e0e90-106">WCF (Windows Communication Foundation) 템플릿에서 서비스 이름을 바꾸려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-106">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="e0e90-107">서비스를 구현하는 클래스 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-107">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="e0e90-108">다음 예제에 표시된 대로 서비스의 구성 파일에서 선택한 새 이름으로 서비스 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-108">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="e0e90-109">구성 파일은 호스팅 모델에 따라 app.config 또는 web.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-109">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="e0e90-110">서비스가 webhosted 인 경우 *\* .svc* 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-110">If your service is webhosted, it uses an *\*.svc* file.</span></span> <span data-ttu-id="e0e90-111">svc 파일을 열고 다음 예제에 표시된 대로 서비스 이름을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-111">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="e0e90-112">svc 파일이 없는 경우 이 단계는 자체 호스팅 애플리케이션에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-112">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="e0e90-113">WCF 서비스 계약 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="e0e90-113">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="e0e90-114">서비스 계약 이름을 바꾸려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-114">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="e0e90-115">서비스 계약 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-115">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="e0e90-116">다음 예제에 표시된 대로 서비스의 구성 파일에서 선택한 새 이름으로 서비스 계약 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-116">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="e0e90-117">구성 파일은 호스팅 모델에 따라 app.config 또는 web.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e0e90-117">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
