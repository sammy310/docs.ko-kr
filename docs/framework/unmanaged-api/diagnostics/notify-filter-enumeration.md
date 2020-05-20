---
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
ms.openlocfilehash: b20e18d5f4314a0ab1442ac7bd5c6514e4db85d5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609484"
---
# <a name="notify_filter-enumeration"></a><span data-ttu-id="4699e-102">NOTIFY_FILTER 열거형</span><span class="sxs-lookup"><span data-stu-id="4699e-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="4699e-103">디버거 함수의 콜백을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="4699e-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="4699e-104">자세한 내용은 [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4699e-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4699e-105">구문</span><span class="sxs-lookup"><span data-stu-id="4699e-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="4699e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4699e-106">Members</span></span>  
  
|<span data-ttu-id="4699e-107">멤버</span><span class="sxs-lookup"><span data-stu-id="4699e-107">Member</span></span>|<span data-ttu-id="4699e-108">설명</span><span class="sxs-lookup"><span data-stu-id="4699e-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="4699e-109">[INotifySink2:: OnSyncCallOut](inotifysink2-onsynccallout-method.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4699e-109">Indicates that the [INotifySink2::OnSyncCallOut](inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="4699e-110">[INotifySink2:: OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4699e-110">Indicates that the [INotifySink2::OnSyncCallEnter](inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="4699e-111">[INotifySink2:: OnSyncCallExit](inotifysink2-onsynccallexit-method.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4699e-111">Indicates that the [INotifySink2::OnSyncCallExit](inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="4699e-112">[INotifySink2:: OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4699e-112">Indicates that the [INotifySink2::OnSyncCallReturn](inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="4699e-113">모든 [INotifySink2](inotifysink2-interface.md) 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4699e-113">Indicates that all of the [INotifySink2](inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="4699e-114">모든 기존 및 향후 알림을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="4699e-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="4699e-115">알림 메서드를 호출 하지 않아야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4699e-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4699e-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4699e-116">Requirements</span></span>  
 <span data-ttu-id="4699e-117">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="4699e-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4699e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4699e-118">See also</span></span>

- [<span data-ttu-id="4699e-119">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="4699e-119">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
