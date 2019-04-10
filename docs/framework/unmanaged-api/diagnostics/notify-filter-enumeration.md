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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63c3ecd0ae0d9e1df62d73eb05b759093583f652
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142885"
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="5a5d3-102">NOTIFY_FILTER 열거형</span><span class="sxs-lookup"><span data-stu-id="5a5d3-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="5a5d3-103">디버거 함수에 대 한 콜백을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d3-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="5a5d3-104">자세한 내용은 참조는 [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5a5d3-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a5d3-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a5d3-105">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="5a5d3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5a5d3-106">Members</span></span>  
  
|<span data-ttu-id="5a5d3-107">멤버</span><span class="sxs-lookup"><span data-stu-id="5a5d3-107">Member</span></span>|<span data-ttu-id="5a5d3-108">설명</span><span class="sxs-lookup"><span data-stu-id="5a5d3-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="5a5d3-109">나타내는 합니다 [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d3-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="5a5d3-110">나타내는 합니다 [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d3-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="5a5d3-111">나타내는 합니다 [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d3-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="5a5d3-112">나타내는 합니다 [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d3-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="5a5d3-113">나타내는 모든 합니다 [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d3-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="5a5d3-114">모든 기존 및 향후 알림을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d3-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="5a5d3-115">없는 알림 메서드를 호출 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a5d3-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a5d3-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a5d3-116">Requirements</span></span>  
 <span data-ttu-id="5a5d3-117">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="5a5d3-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a5d3-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a5d3-118">See also</span></span>

- [<span data-ttu-id="5a5d3-119">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="5a5d3-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
