---
title: INotifySource2::SetNotifyFilter 메서드
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37e4abeebce155a4c332e864b4dfb6cf5a1141ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151751"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="1444a-102">INotifySource2::SetNotifyFilter 메서드</span><span class="sxs-lookup"><span data-stu-id="1444a-102">INotifySource2::SetNotifyFilter Method</span></span>
<span data-ttu-id="1444a-103">이 원본 사용에 대 한 알림 필터를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1444a-103">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1444a-104">구문</span><span class="sxs-lookup"><span data-stu-id="1444a-104">Syntax</span></span>  
  
```  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1444a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1444a-105">Parameters</span></span>  
 `in_NotifyFilter`  
 <span data-ttu-id="1444a-106">[in] 비트 조합 합니다 [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) 디버거 API에 대 한 콜백을 식별 하는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1444a-106">[in] A bitwise combination of the [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="1444a-107">[in] 에 대 한 포인터를 [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) 디버거 API에 대 한 스레드를 식별 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="1444a-107">[in] A pointer to a [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1444a-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="1444a-108">Return Value</span></span>  
 <span data-ttu-id="1444a-109">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="1444a-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1444a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1444a-110">Requirements</span></span>  
 <span data-ttu-id="1444a-111">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="1444a-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1444a-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="1444a-112">See also</span></span>

- [<span data-ttu-id="1444a-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1444a-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="1444a-114">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1444a-114">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="1444a-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1444a-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
