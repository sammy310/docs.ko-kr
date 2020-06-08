---
title: COR_PRF_STATIC_TYPE 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 80d72aefc736054afcee152c55e941c0f8f3c6a8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500769"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="38286-102">COR_PRF_STATIC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="38286-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="38286-103">필드가 정적인지 여부와 정적인 경우 필드에 적용될 정적 품질을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38286-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="38286-104">비트 OR 연산을 사용 하 여 이러한 값을 결합 하 여 필드에 여러 다른 정적 품질이 있음을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38286-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38286-105">구문</span><span class="sxs-lookup"><span data-stu-id="38286-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="38286-106">멤버</span><span class="sxs-lookup"><span data-stu-id="38286-106">Members</span></span>  
  
|<span data-ttu-id="38286-107">멤버</span><span class="sxs-lookup"><span data-stu-id="38286-107">Member</span></span>|<span data-ttu-id="38286-108">설명</span><span class="sxs-lookup"><span data-stu-id="38286-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="38286-109">필드가 static이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="38286-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="38286-110">응용 프로그램 도메인-정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="38286-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="38286-111">이 필드는 스레드 정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="38286-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="38286-112">정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="38286-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="38286-113">RVA (상대 가상 주소)-정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="38286-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38286-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38286-114">Requirements</span></span>  
 <span data-ttu-id="38286-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38286-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38286-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38286-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38286-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38286-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38286-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38286-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38286-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38286-119">See also</span></span>

- [<span data-ttu-id="38286-120">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="38286-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
