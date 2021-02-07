---
description: '다음에 대 한 자세한 정보: 열거형 MALLOC_TYPE'
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
ms.openlocfilehash: 47eb58107d79309c34af5f0acdf614804d1f208f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679804"
---
# <a name="malloc_type-enumeration"></a><span data-ttu-id="2d993-103">MALLOC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="2d993-103">MALLOC_TYPE Enumeration</span></span>

<span data-ttu-id="2d993-104">할당 되는 메모리의 특성을 지정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d993-104">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d993-105">구문</span><span class="sxs-lookup"><span data-stu-id="2d993-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="2d993-106">구성원</span><span class="sxs-lookup"><span data-stu-id="2d993-106">Members</span></span>  
  
|<span data-ttu-id="2d993-107">멤버</span><span class="sxs-lookup"><span data-stu-id="2d993-107">Member</span></span>|<span data-ttu-id="2d993-108">설명</span><span class="sxs-lookup"><span data-stu-id="2d993-108">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="2d993-109">할당 된 메모리는 실행 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d993-109">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="2d993-110">할당 된 메모리는 스레드로부터 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d993-110">The allocated memory is thread-safe.</span></span> <span data-ttu-id="2d993-111">즉, 동기화 하지 않고 여러 스레드를 사용 하 여 메모리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d993-111">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="2d993-112">이 플래그를 설정 하지 않으면 개체에 대 한 호출을 직렬화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d993-112">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d993-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d993-113">Requirements</span></span>  

 <span data-ttu-id="2d993-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d993-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d993-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2d993-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d993-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d993-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d993-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d993-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d993-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d993-118">See also</span></span>

- [<span data-ttu-id="2d993-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="2d993-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
