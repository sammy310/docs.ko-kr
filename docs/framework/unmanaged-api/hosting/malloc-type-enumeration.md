---
title: MALLOC_TYPE 열거형
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695f69c8d9c3a295a705971743733339cf8aab13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211948"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="587c0-102">MALLOC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="587c0-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="587c0-103">할당 되는 메모리의 특징을 지정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="587c0-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="587c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="587c0-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="587c0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="587c0-105">Members</span></span>  
  
|<span data-ttu-id="587c0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="587c0-106">Member</span></span>|<span data-ttu-id="587c0-107">설명</span><span class="sxs-lookup"><span data-stu-id="587c0-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="587c0-108">할당된 된 메모리는 실행 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="587c0-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="587c0-109">할당된 된 메모리는 스레드로부터 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="587c0-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="587c0-110">즉, 메모리 동기화 없이 여러 스레드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="587c0-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="587c0-111">이 플래그를 설정 하지 않으면 개체에 대 한 호출이 serialize 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="587c0-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="587c0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="587c0-112">Requirements</span></span>  
 <span data-ttu-id="587c0-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="587c0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="587c0-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="587c0-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="587c0-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="587c0-115">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="587c0-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="587c0-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="587c0-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="587c0-117">See also</span></span>

- [<span data-ttu-id="587c0-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="587c0-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
