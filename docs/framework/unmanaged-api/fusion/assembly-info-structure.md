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
ms.openlocfilehash: bae19ec18c54eccc7aa54d2d3a006f36ba8ab762
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110879"
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="edb62-102">ASSEMBLY_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="edb62-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="edb62-103">전역 어셈블리 캐시에 등록 된 어셈블리에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edb62-104">구문</span><span class="sxs-lookup"><span data-stu-id="edb62-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="edb62-105">멤버</span><span class="sxs-lookup"><span data-stu-id="edb62-105">Members</span></span>  
  
|<span data-ttu-id="edb62-106">멤버</span><span class="sxs-lookup"><span data-stu-id="edb62-106">Member</span></span>|<span data-ttu-id="edb62-107">설명</span><span class="sxs-lookup"><span data-stu-id="edb62-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="edb62-108">구조체의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="edb62-109">이 필드는 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="edb62-110">어셈블리에 대 한 설치 세부 정보를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="edb62-111">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="edb62-112">어셈블리가 설치 되어 있는지 여부를 나타내는-ASSEMBLYINFO_FLAG_INSTALLED 값입니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="edb62-113">.NET Framework의 현재 버전을 항상 설정 `dwAssemblyFlags` 이 값으로.</span><span class="sxs-lookup"><span data-stu-id="edb62-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="edb62-114">어셈블리에 상주 하는 페이로드를 나타내는-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="edb62-115">.NET Framework의 현재 버전을 설정 하지 `dwAssemblyFlags` 이 값으로.</span><span class="sxs-lookup"><span data-stu-id="edb62-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="edb62-116">(킬로바이트) 어셈블리에 있는 파일의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="edb62-117">매니페스트 파일에 대 한 현재 경로 포함 하는 문자열 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="edb62-118">경로 null 문자로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="edb62-119">Null 종결자를 포함 하 여 와이드 문자 수는 `pszCurrentAssemblyPathBuf` 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb62-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="edb62-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="edb62-120">Requirements</span></span>  
 <span data-ttu-id="edb62-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="edb62-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edb62-122">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="edb62-122">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="edb62-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="edb62-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="edb62-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="edb62-124">See also</span></span>

- [<span data-ttu-id="edb62-125">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="edb62-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [<span data-ttu-id="edb62-126">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="edb62-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
