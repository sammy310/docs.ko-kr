---
description: '다음에 대 한 자세한 정보: FUSION_INSTALL_REFERENCE 구조체'
title: FUSION_INSTALL_REFERENCE 구조체
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
ms.openlocfilehash: 4ac3d2f7d36dd017315a8a3ce6d6185e75f9ddc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761111"
---
# <a name="fusion_install_reference-structure"></a><span data-ttu-id="09fc4-103">FUSION_INSTALL_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="09fc4-103">FUSION_INSTALL_REFERENCE Structure</span></span>

<span data-ttu-id="09fc4-104">응용 프로그램이 전역 어셈블리 캐시에 설치 된 어셈블리에 대해 수행 하는 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-104">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09fc4-105">구문</span><span class="sxs-lookup"><span data-stu-id="09fc4-105">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="09fc4-106">구성원</span><span class="sxs-lookup"><span data-stu-id="09fc4-106">Members</span></span>  
  
|<span data-ttu-id="09fc4-107">멤버</span><span class="sxs-lookup"><span data-stu-id="09fc4-107">Member</span></span>|<span data-ttu-id="09fc4-108">설명</span><span class="sxs-lookup"><span data-stu-id="09fc4-108">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="09fc4-109">구조체의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-109">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="09fc4-110">향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-110">Reserved for future extensibility.</span></span> <span data-ttu-id="09fc4-111">이 값은 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-111">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="09fc4-112">참조를 추가 하는 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-112">The entity that adds the reference.</span></span> <span data-ttu-id="09fc4-113">이 필드에는 다음 값 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-113">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="09fc4-114">-FUSION_REFCOUNT_MSI_GUID: Microsoft Windows Installer를 사용 하 여 설치 된 응용 프로그램에서 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-114">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="09fc4-115">`szIdentifier`필드가로 설정 되 `MSI` 고 `szNonCanonicalData` 필드가로 설정 됩니다 `Windows Installer` .</span><span class="sxs-lookup"><span data-stu-id="09fc4-115">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="09fc4-116">이 체계는 Windows side-by-side 어셈블리에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-116">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="09fc4-117">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: 어셈블리는 **프로그램 추가/제거** 인터페이스에 표시 되는 응용 프로그램에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-117">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="09fc4-118">`szIdentifier`이 필드는 응용 프로그램 **추가/제거** 인터페이스를 사용 하 여 응용 프로그램을 등록 하는 토큰을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-118">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="09fc4-119">-FUSION_REFCOUNT_FILEPATH_GUID: 파일 시스템에서 파일이 나타내는 응용 프로그램에서 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-119">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="09fc4-120">`szIdentifier`필드는이 파일에 대 한 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-120">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="09fc4-121">-FUSION_REFCOUNT_OPAQUE_STRING_GUID: 불투명 문자열만 표시 하는 응용 프로그램에서 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-121">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="09fc4-122">`szIdentifier`필드는이 불투명 문자열을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-122">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="09fc4-123">이 값을 제거 하면 전역 어셈블리 캐시에서 불투명 참조가 있는지 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-123">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="09fc4-124">-FUSION_REFCOUNT_OSINSTALL_GUID:이 값은 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-124">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="09fc4-125">전역 어셈블리 캐시에 어셈블리를 설치한 응용 프로그램을 식별 하는 고유한 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-125">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="09fc4-126">해당 값은 필드의 값에 따라 달라 집니다 `guidScheme` .</span><span class="sxs-lookup"><span data-stu-id="09fc4-126">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="09fc4-127">참조를 추가 하는 엔터티에서 인식할 수 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-127">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="09fc4-128">전역 어셈블리 캐시는이 문자열을 저장 하지만 사용 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09fc4-128">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09fc4-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09fc4-129">Requirements</span></span>  

 <span data-ttu-id="09fc4-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09fc4-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09fc4-131">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="09fc4-131">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="09fc4-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09fc4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09fc4-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09fc4-133">See also</span></span>

- [<span data-ttu-id="09fc4-134">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="09fc4-134">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="09fc4-135">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="09fc4-135">Global Assembly Cache</span></span>](../../app-domains/gac.md)
