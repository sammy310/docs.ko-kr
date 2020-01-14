---
title: RUNTIME_INFO_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: 9d505b917c343c40c7fa2a7aecf3466578ae0a8d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936634"
---
# <a name="runtime_info_flags-enumeration"></a><span data-ttu-id="b60fc-102">RUNTIME_INFO_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="b60fc-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="b60fc-103">반환 해야 하는 CLR (공용 언어 런타임)에 대 한 정보를 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b60fc-104">구문</span><span class="sxs-lookup"><span data-stu-id="b60fc-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b60fc-105">Members</span><span class="sxs-lookup"><span data-stu-id="b60fc-105">Members</span></span>  
  
|<span data-ttu-id="b60fc-106">Member</span><span class="sxs-lookup"><span data-stu-id="b60fc-106">Member</span></span>|<span data-ttu-id="b60fc-107">설명</span><span class="sxs-lookup"><span data-stu-id="b60fc-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="b60fc-108">디렉터리 정보를 포함 하지 않아야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="b60fc-109">버전 정보를 포함 하지 않아야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="b60fc-110">오류가 발생 한 경우 오류 대화 상자를 표시 하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="b60fc-111">SEM_FAILCRITICALERRORS 플래그를 사용 하 여 [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) 함수를 호출 하는 효과를 재정의 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-111">Indicates that the effects of calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="b60fc-112">즉, 실패 시 설치 대화 상자가 표시 되지 않고 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="b60fc-113">AMD-64 호환 버전의 런타임 정보에 대 한 요청을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="b60fc-114">64 호환 버전의 런타임에 대 한 정보에 대 한 요청을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="b60fc-115">X86 호환 버전의 런타임에 대 한 정보 요청을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="b60fc-116">버전 업그레이드 정보를 포함 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b60fc-117">주의</span><span class="sxs-lookup"><span data-stu-id="b60fc-117">Remarks</span></span>  
 <span data-ttu-id="b60fc-118">다음 플랫폼 아키텍처 플래그는 한 번에 하나만 지정할 수 있으며 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b60fc-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="b60fc-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="b60fc-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="b60fc-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="b60fc-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="b60fc-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="b60fc-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b60fc-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b60fc-122">Requirements</span></span>  
 <span data-ttu-id="b60fc-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b60fc-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b60fc-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b60fc-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b60fc-125">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b60fc-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b60fc-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b60fc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60fc-127">참조</span><span class="sxs-lookup"><span data-stu-id="b60fc-127">See also</span></span>

- [<span data-ttu-id="b60fc-128">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="b60fc-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
