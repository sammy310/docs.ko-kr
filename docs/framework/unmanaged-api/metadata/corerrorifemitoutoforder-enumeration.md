---
description: '자세히 알아보기: CorErrorIfEmitOutOfOrder 열거형'
title: CorErrorIfEmitOutOfOrder 열거형
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: b45d3204ae386b7ad9d7ab1daccdfdef35e2ad9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784525"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="3912a-103">CorErrorIfEmitOutOfOrder 열거형</span><span class="sxs-lookup"><span data-stu-id="3912a-103">CorErrorIfEmitOutOfOrder Enumeration</span></span>

<span data-ttu-id="3912a-104">메타데이터를 내보내는 순서가 잘못되었을 때 오류 메시지가 생성되어야 하는 조건을 나타내는 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3912a-104">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3912a-105">구문</span><span class="sxs-lookup"><span data-stu-id="3912a-105">Syntax</span></span>  
  
```cpp  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="3912a-106">구성원</span><span class="sxs-lookup"><span data-stu-id="3912a-106">Members</span></span>  
  
|<span data-ttu-id="3912a-107">멤버</span><span class="sxs-lookup"><span data-stu-id="3912a-107">Member</span></span>|<span data-ttu-id="3912a-108">설명</span><span class="sxs-lookup"><span data-stu-id="3912a-108">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="3912a-109">오류 메시지를 생성 하지 않는 기본 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3912a-109">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="3912a-110">컴파일러가 오류 메시지를 생성 하지 않아야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3912a-110">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="3912a-111">필드, 속성, 이벤트, 메서드 또는 매개 변수가 잘못 된 순서로 내보내지는 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3912a-111">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="3912a-112">메서드가 잘못 된 순서로 내보내지는 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3912a-112">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="3912a-113">필드가 잘못 된 순서로 내보내지는 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3912a-113">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="3912a-114">매개 변수가 잘못 된 순서로 내보내지는 경우 컴파일러가 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3912a-114">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="3912a-115">속성이 잘못 된 순서로 내보내지는 경우 컴파일러가 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3912a-115">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="3912a-116">이벤트가 잘못 된 순서로 내보내지는 경우 컴파일러에서 오류 메시지를 생성 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3912a-116">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3912a-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3912a-117">Requirements</span></span>  

 <span data-ttu-id="3912a-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3912a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3912a-119">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="3912a-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3912a-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3912a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3912a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3912a-121">See also</span></span>

- [<span data-ttu-id="3912a-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="3912a-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
