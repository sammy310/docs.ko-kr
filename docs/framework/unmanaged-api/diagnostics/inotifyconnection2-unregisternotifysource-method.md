---
title: INotifyConnection2::UnregisterNotifySource 메서드
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8b7125ad38bcec773fa2afa8eca09c1d56d90591
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475773"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="92df5-102">INotifyConnection2::UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="92df5-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="92df5-103">연결에서 지정 된 알림 원본 개체를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="92df5-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92df5-104">구문</span><span class="sxs-lookup"><span data-stu-id="92df5-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92df5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92df5-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="92df5-106">[in] 알림 등록을 취소할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="92df5-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92df5-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="92df5-107">Return Value</span></span>  
 <span data-ttu-id="92df5-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="92df5-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92df5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92df5-109">Requirements</span></span>  
 <span data-ttu-id="92df5-110">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="92df5-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92df5-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="92df5-111">See also</span></span>
- [<span data-ttu-id="92df5-112">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92df5-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="92df5-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92df5-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="92df5-114">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92df5-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="92df5-115">RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="92df5-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
