---
description: '자세히 알아보기: CorMethodSemanticsAttr 열거형'
title: CorMethodSemanticsAttr 열거형
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 4079e81ae2389ff0684fd11d0751b191a7289932
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784368"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="7499b-103">CorMethodSemanticsAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="7499b-103">CorMethodSemanticsAttr Enumeration</span></span>

<span data-ttu-id="7499b-104">메서드와 관련 속성 또는 이벤트 간의 관계를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7499b-104">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7499b-105">구문</span><span class="sxs-lookup"><span data-stu-id="7499b-105">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="7499b-106">구성원</span><span class="sxs-lookup"><span data-stu-id="7499b-106">Members</span></span>  
  
|<span data-ttu-id="7499b-107">멤버</span><span class="sxs-lookup"><span data-stu-id="7499b-107">Member</span></span>|<span data-ttu-id="7499b-108">설명</span><span class="sxs-lookup"><span data-stu-id="7499b-108">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="7499b-109">메서드가 `set` 속성의 접근자 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7499b-109">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="7499b-110">메서드가 `get` 속성의 접근자 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7499b-110">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="7499b-111">메서드가 속성 또는 여기에 정의 된 이벤트 이외의 이벤트와 관계가 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7499b-111">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="7499b-112">메서드가 이벤트에 대 한 처리기 메서드를 추가 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7499b-112">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="7499b-113">메서드가 이벤트에 대 한 처리기 메서드를 제거 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7499b-113">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="7499b-114">메서드가 이벤트를 발생 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7499b-114">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7499b-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7499b-115">Requirements</span></span>  

 <span data-ttu-id="7499b-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7499b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7499b-117">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="7499b-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7499b-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7499b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7499b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7499b-119">See also</span></span>

- [<span data-ttu-id="7499b-120">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="7499b-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
