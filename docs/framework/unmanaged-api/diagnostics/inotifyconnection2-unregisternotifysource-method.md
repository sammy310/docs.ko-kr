---
description: '자세히 알아보기: INotifyConnection2:: UnregisterNotifySource 메서드'
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
ms.openlocfilehash: d3b82665375f54d33b6a5581241788d828060a83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800307"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="4222d-103">INotifyConnection2::UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="4222d-103">INotifyConnection2::UnregisterNotifySource Method</span></span>

<span data-ttu-id="4222d-104">지정 된 알림 소스 개체를 연결에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4222d-104">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4222d-105">구문</span><span class="sxs-lookup"><span data-stu-id="4222d-105">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4222d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4222d-106">Parameters</span></span>  

 `in_pNotifySource`  
 <span data-ttu-id="4222d-107">진행 등록을 취소할 알림 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4222d-107">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4222d-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="4222d-108">Return Value</span></span>  

 <span data-ttu-id="4222d-109">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="4222d-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4222d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4222d-110">Requirements</span></span>  

 <span data-ttu-id="4222d-111">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="4222d-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4222d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4222d-112">See also</span></span>

- [<span data-ttu-id="4222d-113">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4222d-113">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="4222d-114">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4222d-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="4222d-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4222d-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="4222d-116">RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="4222d-116">RegisterNotifySource Method</span></span>](inotifyconnection2-registernotifysource-method.md)
