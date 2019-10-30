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
ms.openlocfilehash: 16f56809b4db159c71b06b3bb9d969f8a8f8fc54
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090832"
---
# <a name="malloc_type-enumeration"></a><span data-ttu-id="85b1f-102">MALLOC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="85b1f-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="85b1f-103">할당 되는 메모리의 특성을 지정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b1f-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85b1f-104">구문</span><span class="sxs-lookup"><span data-stu-id="85b1f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="85b1f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="85b1f-105">Members</span></span>  
  
|<span data-ttu-id="85b1f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="85b1f-106">Member</span></span>|<span data-ttu-id="85b1f-107">설명</span><span class="sxs-lookup"><span data-stu-id="85b1f-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="85b1f-108">할당 된 메모리는 실행 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b1f-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="85b1f-109">할당 된 메모리는 스레드로부터 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b1f-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="85b1f-110">즉, 동기화 하지 않고 여러 스레드를 사용 하 여 메모리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b1f-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="85b1f-111">이 플래그를 설정 하지 않으면 개체에 대 한 호출을 직렬화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b1f-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85b1f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85b1f-112">Requirements</span></span>  
 <span data-ttu-id="85b1f-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85b1f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85b1f-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="85b1f-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85b1f-115">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="85b1f-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85b1f-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85b1f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b1f-117">참조</span><span class="sxs-lookup"><span data-stu-id="85b1f-117">See also</span></span>

- [<span data-ttu-id="85b1f-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="85b1f-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
