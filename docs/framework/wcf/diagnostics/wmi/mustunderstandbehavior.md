---
description: '자세히 알아보기: MustUnderstandBehavior'
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 173548f2f3346a79bf7f53c90384db94a638a366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803128"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="96020-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="96020-103">MustUnderstandBehavior</span></span>

<span data-ttu-id="96020-104">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="96020-104">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96020-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="96020-105">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="96020-106">메서드</span><span class="sxs-lookup"><span data-stu-id="96020-106">Methods</span></span>  

 <span data-ttu-id="96020-107">MustUnderstandBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96020-107">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="96020-108">속성</span><span class="sxs-lookup"><span data-stu-id="96020-108">Properties</span></span>  

 <span data-ttu-id="96020-109">MustUnderstandBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96020-109">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="96020-110">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="96020-110">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="96020-111">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="96020-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="96020-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="96020-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="96020-113">이 속성이 `true`인 경우 처리되지 않은 `MustUnderstand` 특성이 있는 모든 SOAP 헤더로 인해 예외를 throw하는 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="96020-113">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96020-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96020-114">Requirements</span></span>  
  
|<span data-ttu-id="96020-115">MOF</span><span class="sxs-lookup"><span data-stu-id="96020-115">MOF</span></span>|<span data-ttu-id="96020-116">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96020-116">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="96020-117">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="96020-117">Namespace</span></span>|<span data-ttu-id="96020-118">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96020-118">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96020-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96020-119">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
