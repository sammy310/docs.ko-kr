---
description: '다음에 대 한 자세한 정보: 열거형 NOTIFY_FILTER'
title: NOTIFY_FILTER 열거형
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
ms.openlocfilehash: 0ed09af0af302b08102b7b08fa72a2d255c5b231
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761488"
---
# <a name="notify_filter-enumeration"></a><span data-ttu-id="f07e9-103">NOTIFY_FILTER 열거형</span><span class="sxs-lookup"><span data-stu-id="f07e9-103">NOTIFY_FILTER Enumeration</span></span>

<span data-ttu-id="f07e9-104">디버거 함수의 콜백을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07e9-104">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="f07e9-105">자세한 내용은 [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f07e9-105">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f07e9-106">구문</span><span class="sxs-lookup"><span data-stu-id="f07e9-106">Syntax</span></span>  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="f07e9-107">구성원</span><span class="sxs-lookup"><span data-stu-id="f07e9-107">Members</span></span>  
  
|<span data-ttu-id="f07e9-108">멤버</span><span class="sxs-lookup"><span data-stu-id="f07e9-108">Member</span></span>|<span data-ttu-id="f07e9-109">설명</span><span class="sxs-lookup"><span data-stu-id="f07e9-109">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="f07e9-110">[INotifySink2:: OnSyncCallOut](inotifysink2-onsynccallout-method.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f07e9-110">Indicates that the [INotifySink2::OnSyncCallOut](inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="f07e9-111">[INotifySink2:: OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f07e9-111">Indicates that the [INotifySink2::OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="f07e9-112">[INotifySink2:: OnSyncCallExit](inotifysink2-onsynccallexit-method.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f07e9-112">Indicates that the [INotifySink2::OnSyncCallExit](inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="f07e9-113">[INotifySink2:: OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f07e9-113">Indicates that the [INotifySink2::OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="f07e9-114">모든 [INotifySink2](inotifysink2-interface.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f07e9-114">Indicates that all of the [INotifySink2](inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="f07e9-115">모든 기존 및 향후 알림을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07e9-115">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="f07e9-116">알림 메서드를 호출 하지 않아야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f07e9-116">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f07e9-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f07e9-117">Requirements</span></span>  

 <span data-ttu-id="f07e9-118">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="f07e9-118">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07e9-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f07e9-119">See also</span></span>

- [<span data-ttu-id="f07e9-120">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="f07e9-120">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
