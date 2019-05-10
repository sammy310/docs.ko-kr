---
title: 인스턴스
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: e0be9c93b5efe17235dbccd426cdd73fbb739361
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651844"
---
# <a name="instances"></a><span data-ttu-id="32d16-102">인스턴스</span><span class="sxs-lookup"><span data-stu-id="32d16-102">Instances</span></span>
<span data-ttu-id="32d16-103">카운터 이름: 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="32d16-104">설명</span><span class="sxs-lookup"><span data-stu-id="32d16-104">Description</span></span>  
 <span data-ttu-id="32d16-105">현재 서비스에 포함된 인스턴스 컨텍스트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="32d16-106">대체로 인스턴스 컨텍스트 수는 인스턴스 수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="32d16-107">그러나 다음 시나리오는 이 규칙의 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="32d16-108">서비스 메서드가 명시적으로 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="32d16-109"><xref:System.ServiceModel.ReleaseInstanceMode>가 <xref:System.ServiceModel.OperationBehaviorAttribute> 인스턴스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="32d16-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d16-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="32d16-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
