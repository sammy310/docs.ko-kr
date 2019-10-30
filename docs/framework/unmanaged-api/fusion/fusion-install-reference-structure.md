---
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
ms.openlocfilehash: 3859752fd92a76f3fef1ceced0e792109b65106a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108287"
---
# <a name="fusion_install_reference-structure"></a><span data-ttu-id="5961e-102">FUSION_INSTALL_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="5961e-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="5961e-103">응용 프로그램이 전역 어셈블리 캐시에 설치 된 어셈블리에 대해 수행 하는 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5961e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5961e-104">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="5961e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5961e-105">Members</span></span>  
  
|<span data-ttu-id="5961e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5961e-106">Member</span></span>|<span data-ttu-id="5961e-107">설명</span><span class="sxs-lookup"><span data-stu-id="5961e-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="5961e-108">구조체의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="5961e-109">향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-109">Reserved for future extensibility.</span></span> <span data-ttu-id="5961e-110">이 값은 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="5961e-111">참조를 추가 하는 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-111">The entity that adds the reference.</span></span> <span data-ttu-id="5961e-112">이 필드에는 다음 값 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="5961e-113">-FUSION_REFCOUNT_MSI_GUID: Microsoft Windows Installer을 사용 하 여 설치 된 응용 프로그램에서 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="5961e-114">`szIdentifier` 필드가 `MSI`로 설정 되 고 `szNonCanonicalData` 필드가 `Windows Installer`로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="5961e-115">이 체계는 Windows side-by-side 어셈블리에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="5961e-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: 어셈블리는 **프로그램 추가/제거** 인터페이스에 표시 되는 응용 프로그램에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="5961e-117">`szIdentifier` 필드는 프로그램 **추가/제거** 인터페이스를 사용 하 여 응용 프로그램을 등록 하는 토큰을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="5961e-118">-FUSION_REFCOUNT_FILEPATH_GUID: 파일 시스템에서 파일이 나타내는 응용 프로그램에서 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="5961e-119">`szIdentifier` 필드는이 파일에 대 한 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="5961e-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID: 불투명 문자열만 표시 하는 응용 프로그램에서 어셈블리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="5961e-121">`szIdentifier` 필드는이 불투명 문자열을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="5961e-122">이 값을 제거 하면 전역 어셈블리 캐시에서 불투명 참조가 있는지 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="5961e-123">-FUSION_REFCOUNT_OSINSTALL_GUID:이 값은 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="5961e-124">전역 어셈블리 캐시에 어셈블리를 설치한 응용 프로그램을 식별 하는 고유한 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="5961e-125">해당 값은 `guidScheme` 필드의 값에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="5961e-126">참조를 추가 하는 엔터티에서 인식할 수 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="5961e-127">전역 어셈블리 캐시는이 문자열을 저장 하지만 사용 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5961e-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5961e-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5961e-128">Requirements</span></span>  
 <span data-ttu-id="5961e-129">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5961e-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5961e-130">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5961e-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5961e-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5961e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5961e-132">참조</span><span class="sxs-lookup"><span data-stu-id="5961e-132">See also</span></span>

- [<span data-ttu-id="5961e-133">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="5961e-133">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="5961e-134">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="5961e-134">Global Assembly Cache</span></span>](../../app-domains/gac.md)
