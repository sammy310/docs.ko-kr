---
title: CorMethodAttr 열거형
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
ms.openlocfilehash: 74088d1cd018bb07406fc7d00ff83d783a98b663
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450234"
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="21d33-102">CorMethodAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="21d33-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="21d33-103">메서드의 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d33-104">구문</span><span class="sxs-lookup"><span data-stu-id="21d33-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="21d33-105">멤버</span><span class="sxs-lookup"><span data-stu-id="21d33-105">Members</span></span>  
  
|<span data-ttu-id="21d33-106">멤버</span><span class="sxs-lookup"><span data-stu-id="21d33-106">Member</span></span>|<span data-ttu-id="21d33-107">설명</span><span class="sxs-lookup"><span data-stu-id="21d33-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="21d33-108">멤버 액세스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="21d33-109">멤버를 참조할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="21d33-110">부모 형식만 멤버에 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="21d33-111">이 어셈블리의 하위 형식에서 멤버에 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="21d33-112">멤버가 어셈블리의 모든 사용자에 의해 accessibly 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="21d33-113">형식 및 하위 형식 에서만 멤버에 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="21d33-114">파생 클래스와 해당 어셈블리의 다른 형식에서 멤버에 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="21d33-115">범위에 대 한 액세스 권한이 있는 모든 형식에서 멤버에 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="21d33-116">멤버가 인스턴스의 멤버가 아니라 형식의 일부로 정의 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="21d33-117">메서드를 재정의할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="21d33-118">메서드를 재정의할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="21d33-119">메서드가 이름 뿐만 아니라 이름 및 시그니처로 숨기도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="21d33-120">가상 테이블 레이아웃을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="21d33-121">가상 테이블에서이 메서드에 사용 되는 슬롯을 다시 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="21d33-122">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="21d33-123">메서드가 항상 가상 테이블에 새 슬롯을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="21d33-124">표시 되는 형식과 동일한 형식으로 메서드를 재정의할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="21d33-125">메서드가 구현 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="21d33-126">메서드를 특수 하 게 지정 하 고 해당 이름에서 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="21d33-127">PInvoke를 사용 하 여 메서드 구현을 전달 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="21d33-128">메서드를 비관리 코드로 내보낸 관리 되는 메서드로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="21d33-129">공용 언어 런타임에서 내부용으로 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="21d33-130">공용 언어 런타임에서 메서드 이름의 인코딩을 확인 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="21d33-131">메서드에 연결 된 보안이 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="21d33-132">메서드가 보안 코드를 포함 하는 다른 메서드를 호출 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d33-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21d33-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21d33-133">Requirements</span></span>  
 <span data-ttu-id="21d33-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21d33-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21d33-135">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="21d33-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="21d33-136">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21d33-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d33-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21d33-137">See also</span></span>

- [<span data-ttu-id="21d33-138">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="21d33-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
