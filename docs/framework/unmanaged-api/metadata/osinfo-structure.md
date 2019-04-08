---
title: OSINFO 구조체
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0aba49fb4a60b2e471c541a8d8531a1cbc8627f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096201"
---
# <a name="osinfo-structure"></a><span data-ttu-id="02541-102">OSINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="02541-102">OSINFO Structure</span></span>
<span data-ttu-id="02541-103">어셈블리 또는 모듈에 대 한 운영 체제에 대 한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="02541-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02541-104">구문</span><span class="sxs-lookup"><span data-stu-id="02541-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="02541-105">멤버</span><span class="sxs-lookup"><span data-stu-id="02541-105">Members</span></span>  
  
|<span data-ttu-id="02541-106">멤버</span><span class="sxs-lookup"><span data-stu-id="02541-106">Member</span></span>|<span data-ttu-id="02541-107">설명</span><span class="sxs-lookup"><span data-stu-id="02541-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="02541-108">Microsoft Windows 플랫폼 함수에 의해 정의 된 식별자 값 중 하나 `GetVersionEx`합니다.</span><span class="sxs-lookup"><span data-stu-id="02541-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="02541-109">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02541-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="02541-110">-VER_PLATFORM_WIN32s, 또는 0x0000, Microsoft Windows 3.1을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02541-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="02541-111">-VER_PLATFORM_WIN32_WINDOWS, 또는 0x0001, Windows 95, Windows 98 또는 운영 체제에서 나온 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02541-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="02541-112">-VER_PLATFORM_WIN32_NT, 또는 0x0010, Windows NT 또는 운영 체제에서 나온 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02541-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="02541-113">운영 체제 주 버전 또는 모든 버전을 나타내는 NULL 값입니다.</span><span class="sxs-lookup"><span data-stu-id="02541-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="02541-114">운영 체제 부 버전, 또는 모든 버전을 나타내는 NULL 값입니다.</span><span class="sxs-lookup"><span data-stu-id="02541-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02541-115">설명</span><span class="sxs-lookup"><span data-stu-id="02541-115">Remarks</span></span>  
 `OSINFO` <span data-ttu-id="02541-116">기반으로 합니다 `OSVERSIONINFOEX` 구조체에서 사용 되는 함수 호출에 Microsoft Windows 플랫폼 `GetVersionEx`합니다.</span><span class="sxs-lookup"><span data-stu-id="02541-116">is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="02541-117">이 구조는 ASSEMBLYMETADATA 구조체에서 해당 운영 체제 지원을 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02541-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02541-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02541-118">Requirements</span></span>  
 <span data-ttu-id="02541-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="02541-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02541-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="02541-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02541-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="02541-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="02541-122">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="02541-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="02541-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="02541-123">See also</span></span>

- [<span data-ttu-id="02541-124">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="02541-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="02541-125">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02541-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
