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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9483cf8671b7d3ad5430081d93925af30b3d8368
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215692"
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="69132-102">RUNTIME_INFO_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="69132-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="69132-103">CLR (공용 언어 런타임)에 대 한 정보를 반환할지 여부를 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="69132-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69132-104">구문</span><span class="sxs-lookup"><span data-stu-id="69132-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="69132-105">멤버</span><span class="sxs-lookup"><span data-stu-id="69132-105">Members</span></span>  
  
|<span data-ttu-id="69132-106">멤버</span><span class="sxs-lookup"><span data-stu-id="69132-106">Member</span></span>|<span data-ttu-id="69132-107">설명</span><span class="sxs-lookup"><span data-stu-id="69132-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="69132-108">디렉터리 정보를 포함 하지 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69132-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="69132-109">버전 정보를 포함 하지 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69132-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="69132-110">실패 시 오류 대화 상자를 표시 되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69132-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="69132-111">나타내는 호출의 결과 [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) SEM_FAILCRITICALERRORS 플래그를 사용 하 여 함수를 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69132-111">Indicates that the effects of calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="69132-112">즉, 설치 대화 상자를 표시 되는 대신 실패 하면 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69132-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="69132-113">런타임의 AMD-64-호환 되는 버전 정보에 대 한 요청을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69132-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="69132-114">런타임의 IA-64-호환 되는 버전 정보에 대 한 요청을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69132-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="69132-115">런타임의 x86 호환 버전 정보에 대 한 요청을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69132-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="69132-116">버전 업그레이드 정보 포함 되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69132-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69132-117">설명</span><span class="sxs-lookup"><span data-stu-id="69132-117">Remarks</span></span>  
 <span data-ttu-id="69132-118">다음 플랫폼 아키텍처 플래그를 한 번에 하나만 지정된 될 수 있습니다 및 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69132-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="69132-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="69132-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="69132-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="69132-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="69132-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="69132-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69132-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69132-122">Requirements</span></span>  
 <span data-ttu-id="69132-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="69132-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69132-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="69132-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69132-125">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69132-125">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="69132-126">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="69132-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="69132-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="69132-127">See also</span></span>

- [<span data-ttu-id="69132-128">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="69132-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
