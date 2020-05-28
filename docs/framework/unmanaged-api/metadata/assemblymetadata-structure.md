---
title: ASSEMBLYMETADATA 구조체
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 5c7211fc2523b70313a1e4d4d9d2da0dcecd1d32
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009433"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="526e3-102">ASSEMBLYMETADATA 구조체</span><span class="sxs-lookup"><span data-stu-id="526e3-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="526e3-103">참조 된 어셈블리에 대 한 버전 및 로캘, 프로세서 및 운영 체제에 대 한 지원 수준을 포함 하 여 참조 되는 어셈블리에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="526e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="526e3-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="526e3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="526e3-105">Members</span></span>  
  
|<span data-ttu-id="526e3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="526e3-106">Member</span></span>|<span data-ttu-id="526e3-107">설명</span><span class="sxs-lookup"><span data-stu-id="526e3-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="526e3-108">참조 된 어셈블리의 주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="526e3-109">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-109">This value cannot be zero.</span></span> <span data-ttu-id="526e3-110">의 모든 비트가 `usMajorVersion` 설정 되어 있으면 주 버전이 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="526e3-111">참조 된 어셈블리의 부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="526e3-112">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-112">This value cannot be zero.</span></span> <span data-ttu-id="526e3-113">의 모든 비트가 설정 된 경우 `usMinorVersion` 부 버전은 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="526e3-114">참조된 어셈블리의 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="526e3-115">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-115">This value cannot be zero.</span></span> <span data-ttu-id="526e3-116">의 모든 비트가 `usBuildNumber` 설정 되어 있으면 빌드 번호가 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="526e3-117">참조 된 어셈블리의 수정 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="526e3-118">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-118">This value cannot be zero.</span></span> <span data-ttu-id="526e3-119">의 모든 비트가 설정 된 경우 `usRevisionNumber` 수정 번호는 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="526e3-120">RFC1766 사양을 준수 하 고 세미콜론으로 구분 된 로캘 이름 목록으로, 참조 된 어셈블리에서 지원 되는 로캘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="526e3-121">Null 값은 로캘과 관련이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-121">A null value indicates locale independence.</span></span> <span data-ttu-id="526e3-122">**참고:**  .NET Framework 버전 1.0에서는 둘 이상의 로캘을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="526e3-123">의 와이드 문자 크기입니다 `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="526e3-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="526e3-124">참조 된 어셈블리에서 지원 되는 프로세서 형식에 대해 Winnt.exe에 정의 된 식별자의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="526e3-125">NULL 값은 프로세서 독립성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="526e3-126">`rdwProcessor` 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="526e3-127">참조 된 어셈블리에서 지 원하는 운영 체제를 지정 하는 [OSINFO](osinfo-structure.md) 인스턴스의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="526e3-128">NULL 값은 운영 체제 독립성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="526e3-129">`rOS` 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="526e3-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="526e3-130">Requirements</span></span>  
 <span data-ttu-id="526e3-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="526e3-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="526e3-132">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="526e3-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="526e3-133">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="526e3-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="526e3-134">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="526e3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="526e3-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="526e3-135">See also</span></span>

- [<span data-ttu-id="526e3-136">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="526e3-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="526e3-137">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="526e3-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="526e3-138">OSINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="526e3-138">OSINFO Structure</span></span>](osinfo-structure.md)
