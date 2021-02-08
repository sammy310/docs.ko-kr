---
description: '자세히 알아보기: OSINFO Structure'
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
ms.openlocfilehash: 5027ef5cf4137aa1e781134b325407e1251fdd31
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799111"
---
# <a name="osinfo-structure"></a><span data-ttu-id="160c3-103">OSINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="160c3-103">OSINFO Structure</span></span>

<span data-ttu-id="160c3-104">어셈블리 또는 모듈의 운영 체제에 대 한 세부 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-104">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="160c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="160c3-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="160c3-106">구성원</span><span class="sxs-lookup"><span data-stu-id="160c3-106">Members</span></span>  
  
|<span data-ttu-id="160c3-107">멤버</span><span class="sxs-lookup"><span data-stu-id="160c3-107">Member</span></span>|<span data-ttu-id="160c3-108">설명</span><span class="sxs-lookup"><span data-stu-id="160c3-108">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="160c3-109">Microsoft Windows 플랫폼 함수에 의해 정의 된 식별자 값 중 하나입니다 `GetVersionEx` .</span><span class="sxs-lookup"><span data-stu-id="160c3-109">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="160c3-110">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-110">The following values are supported:</span></span><br /><br /> <span data-ttu-id="160c3-111">-VER_PLATFORM_WIN32s 또는 경우 Microsoft Windows 3.1을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-111">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="160c3-112">-VER_PLATFORM_WIN32_WINDOWS 또는 0x0001에서 Windows 95, Windows 98 또는 운영 체제를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-112">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="160c3-113">-VER_PLATFORM_WIN32_NT 또는 0x0002, Windows NT 또는 운영 체제를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-113">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="160c3-114">운영 체제 주 버전 또는 모든 버전을 나타내는 NULL 값입니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-114">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="160c3-115">운영 체제 부 버전 또는 모든 버전을 나타내는 NULL 값입니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-115">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="160c3-116">설명</span><span class="sxs-lookup"><span data-stu-id="160c3-116">Remarks</span></span>  

 <span data-ttu-id="160c3-117">`OSINFO` 는 `OSVERSIONINFOEX` Microsoft Windows 플랫폼 함수 호출에 사용 되는 구조를 기반으로 `GetVersionEx` 합니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-117">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="160c3-118">이 구조는 ASSEMBLYMETADATA 구조에서 해당 운영 체제 지원을 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-118">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="160c3-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="160c3-119">Requirements</span></span>  

 <span data-ttu-id="160c3-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="160c3-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="160c3-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="160c3-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="160c3-122">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="160c3-122">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="160c3-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="160c3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="160c3-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="160c3-124">See also</span></span>

- [<span data-ttu-id="160c3-125">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="160c3-125">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="160c3-126">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="160c3-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
