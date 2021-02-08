---
description: '자세히 알아보기: INotifySource2:: SetNotifyFilter 메서드'
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
ms.openlocfilehash: 2aaf2a5253f8a9acb67c4b538f109a7a62559d12
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800229"
---
# <a name="inotifysource2setnotifyfilter-method"></a><span data-ttu-id="647be-103">INotifySource2::SetNotifyFilter 메서드</span><span class="sxs-lookup"><span data-stu-id="647be-103">INotifySource2::SetNotifyFilter Method</span></span>

<span data-ttu-id="647be-104">이 원본에 사용할 알림 필터를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="647be-104">Assigns a notification filter for use with this source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="647be-105">구문</span><span class="sxs-lookup"><span data-stu-id="647be-105">Syntax</span></span>  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="647be-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="647be-106">Parameters</span></span>  

 `in_NotifyFilter`  
 <span data-ttu-id="647be-107">진행 디버거 API에 대 한 콜백을 식별 하는 [NOTIFY_FILTER](notify-filter-enumeration.md) 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="647be-107">[in] A bitwise combination of the [NOTIFY_FILTER](notify-filter-enumeration.md) enumeration values that identify callbacks for the debugger API.</span></span>  
  
 `in_pUserThreadFilter`  
 <span data-ttu-id="647be-108">진행 디버거 API에 대 한 스레드를 식별 하는 [USER_THREAD](user-thread-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="647be-108">[in] A pointer to a [USER_THREAD](user-thread-structure.md) structure that identifies threads for the debugger API.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="647be-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="647be-109">Return Value</span></span>  

 <span data-ttu-id="647be-110">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="647be-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="647be-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="647be-111">Requirements</span></span>  

 <span data-ttu-id="647be-112">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="647be-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647be-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="647be-113">See also</span></span>

- [<span data-ttu-id="647be-114">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="647be-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="647be-115">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="647be-115">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="647be-116">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="647be-116">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
