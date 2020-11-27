---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 243c9112dd9caf5c92ef77aa0f45b4b1e71a4e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273258"
---
# <a name="serviceappdomain"></a><span data-ttu-id="415ab-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="415ab-102">ServiceAppDomain</span></span>

<span data-ttu-id="415ab-103">서비스를 애플리케이션 도메인에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="415ab-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="415ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="415ab-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="415ab-105">메서드</span><span class="sxs-lookup"><span data-stu-id="415ab-105">Methods</span></span>  

 <span data-ttu-id="415ab-106">ServiceAppDomain 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="415ab-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="415ab-107">속성</span><span class="sxs-lookup"><span data-stu-id="415ab-107">Properties</span></span>  

 <span data-ttu-id="415ab-108">ServiceAppDomain 클래스에는 다음 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="415ab-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="415ab-109">ref</span><span class="sxs-lookup"><span data-stu-id="415ab-109">ref</span></span>  

 <span data-ttu-id="415ab-110">데이터 형식: Service</span><span class="sxs-lookup"><span data-stu-id="415ab-110">Data type: Service</span></span>  
<span data-ttu-id="415ab-111">한정자: Key</span><span class="sxs-lookup"><span data-stu-id="415ab-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="415ab-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="415ab-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="415ab-113">이 애플리케이션 도메인의 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="415ab-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="415ab-114">ref</span><span class="sxs-lookup"><span data-stu-id="415ab-114">ref</span></span>  

 <span data-ttu-id="415ab-115">데이터 형식: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="415ab-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="415ab-116">한정자: Key</span><span class="sxs-lookup"><span data-stu-id="415ab-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="415ab-117">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="415ab-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="415ab-118">애플리케이션 도메인의 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="415ab-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="415ab-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="415ab-119">Requirements</span></span>  
  
|<span data-ttu-id="415ab-120">MOF</span><span class="sxs-lookup"><span data-stu-id="415ab-120">MOF</span></span>|<span data-ttu-id="415ab-121">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="415ab-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="415ab-122">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="415ab-122">Namespace</span></span>|<span data-ttu-id="415ab-123">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="415ab-123">Defined in root\ServiceModel</span></span>|
