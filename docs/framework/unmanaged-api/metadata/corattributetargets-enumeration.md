---
title: CorAttributeTargets 열거형
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: fbe721bad56ec2be434039f00e741ad9a177815f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718971"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="e08a2-102">CorAttributeTargets 열거형</span><span class="sxs-lookup"><span data-stu-id="e08a2-102">CorAttributeTargets Enumeration</span></span>

<span data-ttu-id="e08a2-103">특성을 적용하는 데 유효한 애플리케이션 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e08a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="e08a2-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="e08a2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e08a2-105">Members</span></span>  
  
|<span data-ttu-id="e08a2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e08a2-106">Member</span></span>|<span data-ttu-id="e08a2-107">설명</span><span class="sxs-lookup"><span data-stu-id="e08a2-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="e08a2-108">특성은 어셈블리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="e08a2-109">특성은 이식 가능한 실행 파일 (.dll 또는 .exe)에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="e08a2-110">특성은 클래스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="e08a2-111">특성은 구조체 즉, 값 형식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="e08a2-112">특성은 열거형에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="e08a2-113">특성은 생성자에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="e08a2-114">특성은 메서드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="e08a2-115">특성은 속성에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="e08a2-116">특성은 필드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="e08a2-117">특성은 이벤트에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="e08a2-118">특성은 인터페이스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="e08a2-119">특성은 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="e08a2-120">특성은 대리자에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="e08a2-121">특성은 제네릭 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="e08a2-122">특성은 모든 애플리케이션 요소에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="e08a2-123">클래스의 멤버에 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e08a2-124">설명</span><span class="sxs-lookup"><span data-stu-id="e08a2-124">Remarks</span></span>  

 <span data-ttu-id="e08a2-125">`CorAttributeTargets`열거형 값을 비트 or 연산으로 결합 하 여 기본 조합을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08a2-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="e08a2-126">는 `CorAttributeTargets` 관리 되는 열거형과 유사 합니다 <xref:System.AttributeTargets?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e08a2-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e08a2-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e08a2-127">Requirements</span></span>  

 <span data-ttu-id="e08a2-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e08a2-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e08a2-129">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="e08a2-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e08a2-130">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e08a2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e08a2-131">참조</span><span class="sxs-lookup"><span data-stu-id="e08a2-131">See also</span></span>

- [<span data-ttu-id="e08a2-132">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="e08a2-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
