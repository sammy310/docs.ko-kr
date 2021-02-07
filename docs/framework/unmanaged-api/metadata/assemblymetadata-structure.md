---
description: '다음에 대 한 자세한 정보: ASSEMBLYMETADATA 구조체'
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
ms.openlocfilehash: 6fc9c03bea3b1413cd3a8421746137e37d43bd90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678941"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="e905f-103">ASSEMBLYMETADATA 구조체</span><span class="sxs-lookup"><span data-stu-id="e905f-103">ASSEMBLYMETADATA Structure</span></span>

<span data-ttu-id="e905f-104">참조 된 어셈블리에 대 한 버전 및 로캘, 프로세서 및 운영 체제에 대 한 지원 수준을 포함 하 여 참조 되는 어셈블리에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-104">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e905f-105">구문</span><span class="sxs-lookup"><span data-stu-id="e905f-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e905f-106">구성원</span><span class="sxs-lookup"><span data-stu-id="e905f-106">Members</span></span>  
  
|<span data-ttu-id="e905f-107">멤버</span><span class="sxs-lookup"><span data-stu-id="e905f-107">Member</span></span>|<span data-ttu-id="e905f-108">설명</span><span class="sxs-lookup"><span data-stu-id="e905f-108">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="e905f-109">참조 된 어셈블리의 주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-109">The major version number of the referenced assembly.</span></span> <span data-ttu-id="e905f-110">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-110">This value cannot be zero.</span></span> <span data-ttu-id="e905f-111">의 모든 비트가 `usMajorVersion` 설정 되어 있으면 주 버전이 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-111">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="e905f-112">참조 된 어셈블리의 부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-112">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="e905f-113">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-113">This value cannot be zero.</span></span> <span data-ttu-id="e905f-114">의 모든 비트가 설정 된 경우 `usMinorVersion` 부 버전은 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-114">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="e905f-115">참조된 어셈블리의 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-115">The build number of the referenced assembly.</span></span> <span data-ttu-id="e905f-116">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-116">This value cannot be zero.</span></span> <span data-ttu-id="e905f-117">의 모든 비트가 `usBuildNumber` 설정 되어 있으면 빌드 번호가 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-117">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="e905f-118">참조 된 어셈블리의 수정 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-118">The revision number of the referenced assembly.</span></span> <span data-ttu-id="e905f-119">이 값은 0 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-119">This value cannot be zero.</span></span> <span data-ttu-id="e905f-120">의 모든 비트가 설정 된 경우 `usRevisionNumber` 수정 번호는 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-120">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="e905f-121">RFC1766 사양을 준수 하 고 세미콜론으로 구분 된 로캘 이름 목록으로, 참조 된 어셈블리에서 지원 되는 로캘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-121">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="e905f-122">Null 값은 로캘과 관련이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-122">A null value indicates locale independence.</span></span> <span data-ttu-id="e905f-123">**참고:**  .NET Framework 버전 1.0에서는 둘 이상의 로캘을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-123">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="e905f-124">의 와이드 문자 크기입니다 `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="e905f-124">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="e905f-125">참조 된 어셈블리에서 지원 되는 프로세서 형식에 대해 Winnt.exe에 정의 된 식별자의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-125">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="e905f-126">NULL 값은 프로세서 독립성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-126">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="e905f-127">`rdwProcessor` 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-127">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="e905f-128">참조 된 어셈블리에서 지 원하는 운영 체제를 지정 하는 [OSINFO](osinfo-structure.md) 인스턴스의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-128">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="e905f-129">NULL 값은 운영 체제 독립성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-129">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="e905f-130">`rOS` 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-130">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e905f-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e905f-131">Requirements</span></span>  

 <span data-ttu-id="e905f-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e905f-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e905f-133">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e905f-133">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e905f-134">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e905f-134">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e905f-135">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e905f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e905f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e905f-136">See also</span></span>

- [<span data-ttu-id="e905f-137">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="e905f-137">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="e905f-138">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e905f-138">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="e905f-139">OSINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="e905f-139">OSINFO Structure</span></span>](osinfo-structure.md)
