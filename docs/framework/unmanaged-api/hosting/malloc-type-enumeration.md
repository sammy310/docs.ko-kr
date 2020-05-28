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
ms.openlocfilehash: 630fe4e79b369bfdefc19be72780f1893090895e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008458"
---
# <a name="malloc_type-enumeration"></a><span data-ttu-id="d2c57-102">MALLOC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="d2c57-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="d2c57-103">할당 되는 메모리의 특성을 지정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c57-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c57-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2c57-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="d2c57-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d2c57-105">Members</span></span>  
  
|<span data-ttu-id="d2c57-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d2c57-106">Member</span></span>|<span data-ttu-id="d2c57-107">설명</span><span class="sxs-lookup"><span data-stu-id="d2c57-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="d2c57-108">할당 된 메모리는 실행 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c57-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="d2c57-109">할당 된 메모리는 스레드로부터 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c57-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="d2c57-110">즉, 동기화 하지 않고 여러 스레드를 사용 하 여 메모리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c57-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="d2c57-111">이 플래그를 설정 하지 않으면 개체에 대 한 호출을 직렬화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c57-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2c57-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2c57-112">Requirements</span></span>  
 <span data-ttu-id="d2c57-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2c57-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2c57-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d2c57-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2c57-115">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d2c57-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2c57-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2c57-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c57-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2c57-117">See also</span></span>

- [<span data-ttu-id="d2c57-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="d2c57-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
