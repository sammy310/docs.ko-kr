---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_STATIC_TYPE'
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
ms.openlocfilehash: b7171fe4e9c536d94109d46ae6cad9201a15bab9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789036"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="73e3a-103">COR_PRF_STATIC_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="73e3a-103">COR_PRF_STATIC_TYPE Enumeration</span></span>

<span data-ttu-id="73e3a-104">필드가 정적인지 여부와 정적인 경우 필드에 적용될 정적 품질을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73e3a-104">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="73e3a-105">비트 OR 연산을 사용 하 여 이러한 값을 결합 하 여 필드에 여러 다른 정적 품질이 있음을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e3a-105">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e3a-106">구문</span><span class="sxs-lookup"><span data-stu-id="73e3a-106">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="73e3a-107">구성원</span><span class="sxs-lookup"><span data-stu-id="73e3a-107">Members</span></span>  
  
|<span data-ttu-id="73e3a-108">멤버</span><span class="sxs-lookup"><span data-stu-id="73e3a-108">Member</span></span>|<span data-ttu-id="73e3a-109">설명</span><span class="sxs-lookup"><span data-stu-id="73e3a-109">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="73e3a-110">필드가 static이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="73e3a-110">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="73e3a-111">응용 프로그램 도메인-정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="73e3a-111">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="73e3a-112">이 필드는 스레드 정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="73e3a-112">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="73e3a-113">정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="73e3a-113">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="73e3a-114">RVA (상대 가상 주소)-정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="73e3a-114">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73e3a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73e3a-115">Requirements</span></span>  

 <span data-ttu-id="73e3a-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73e3a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73e3a-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="73e3a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="73e3a-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73e3a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73e3a-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73e3a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e3a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73e3a-120">See also</span></span>

- [<span data-ttu-id="73e3a-121">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="73e3a-121">Profiling Enumerations</span></span>](profiling-enumerations.md)
