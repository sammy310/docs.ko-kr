---
title: ASSEMBLY_INFO 구조체
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 390ab4881396bbc01337d087f05b6066153bfed1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795493"
---
# <a name="assembly_info-structure"></a><span data-ttu-id="050f1-102">ASSEMBLY_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="050f1-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="050f1-103">전역 어셈블리 캐시에 등록 된 어셈블리에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="050f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="050f1-104">Syntax</span></span>  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="050f1-105">멤버</span><span class="sxs-lookup"><span data-stu-id="050f1-105">Members</span></span>  
  
|<span data-ttu-id="050f1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="050f1-106">Member</span></span>|<span data-ttu-id="050f1-107">설명</span><span class="sxs-lookup"><span data-stu-id="050f1-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="050f1-108">구조체의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="050f1-109">이 필드는 나중에 확장할 수 있도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="050f1-110">어셈블리에 대 한 설치 세부 정보를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="050f1-111">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="050f1-112">-어셈블리가 설치 되었음을 나타내는 ASSEMBLYINFO_FLAG_INSTALLED 값입니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="050f1-113">.NET Framework의 현재 버전은 항상이 값 `dwAssemblyFlags` 으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="050f1-114">-어셈블리가 페이로드가 있음을 나타내는 ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="050f1-115">.NET Framework의 현재 버전은이 값으로 `dwAssemblyFlags` 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="050f1-116">어셈블리에 포함 된 파일의 총 크기 (kb)입니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="050f1-117">매니페스트 파일의 현재 경로를 포함 하는 문자열 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="050f1-118">경로는 null 문자로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="050f1-119">을 포함 하는 null 종결자를 포함 하 `pszCurrentAssemblyPathBuf` 는 와이드 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="050f1-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="050f1-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="050f1-120">Requirements</span></span>  
 <span data-ttu-id="050f1-121">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="050f1-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="050f1-122">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="050f1-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="050f1-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="050f1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="050f1-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="050f1-124">See also</span></span>

- [<span data-ttu-id="050f1-125">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="050f1-125">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="050f1-126">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="050f1-126">Global Assembly Cache</span></span>](../../app-domains/gac.md)
