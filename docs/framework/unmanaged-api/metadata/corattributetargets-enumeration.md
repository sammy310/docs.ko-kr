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
ms.openlocfilehash: 51741aa3a6d965c1e9743081628d8ad62e8fb04e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176203"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="d12d1-102">CorAttributeTargets 열거형</span><span class="sxs-lookup"><span data-stu-id="d12d1-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="d12d1-103">특성을 적용하는 데 유효한 애플리케이션 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d12d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="d12d1-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="d12d1-105">구성원</span><span class="sxs-lookup"><span data-stu-id="d12d1-105">Members</span></span>  
  
|<span data-ttu-id="d12d1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d12d1-106">Member</span></span>|<span data-ttu-id="d12d1-107">Description</span><span class="sxs-lookup"><span data-stu-id="d12d1-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="d12d1-108">특성은 어셈블리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="d12d1-109">특성은 휴대용 실행 (.dll 또는 .exe) 모듈에 적용 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="d12d1-110">특성은 클래스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="d12d1-111">특성은 구조체 즉, 값 형식에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="d12d1-112">특성은 열거형에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="d12d1-113">특성은 생성자에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="d12d1-114">특성은 메서드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="d12d1-115">특성은 속성에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="d12d1-116">특성은 필드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="d12d1-117">특성은 이벤트에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="d12d1-118">특성은 인터페이스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="d12d1-119">특성은 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="d12d1-120">특성은 대리자에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="d12d1-121">특성은 제네릭 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="d12d1-122">특성은 모든 애플리케이션 요소에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="d12d1-123">특성은 클래스의 멤버에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d12d1-124">설명</span><span class="sxs-lookup"><span data-stu-id="d12d1-124">Remarks</span></span>  
 <span data-ttu-id="d12d1-125">열거 값은 `CorAttributeTargets` 기본 조합을 얻기 위해 비트 OR 연산을 조합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="d12d1-126">`CorAttributeTargets` 관리되는 <xref:System.AttributeTargets?displayProperty=nameWithType> 열거형과 평행합니다.</span><span class="sxs-lookup"><span data-stu-id="d12d1-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d12d1-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d12d1-127">Requirements</span></span>  
 <span data-ttu-id="d12d1-128">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d12d1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d12d1-129">**헤더:** 코르Hdr.h</span><span class="sxs-lookup"><span data-stu-id="d12d1-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d12d1-130">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d12d1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d12d1-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d12d1-131">See also</span></span>

- [<span data-ttu-id="d12d1-132">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="d12d1-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
