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
ms.openlocfilehash: 90220c2bfea683ff0472473e180c9e11ea568672
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720037"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="e5ae8-102">INotifyConnection2::UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="e5ae8-102">INotifyConnection2::UnregisterNotifySource Method</span></span>

<span data-ttu-id="e5ae8-103">지정 된 알림 소스 개체를 연결에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5ae8-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ae8-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5ae8-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5ae8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5ae8-105">Parameters</span></span>  

 `in_pNotifySource`  
 <span data-ttu-id="e5ae8-106">진행 등록을 취소할 알림 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e5ae8-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5ae8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e5ae8-107">Return Value</span></span>  

 <span data-ttu-id="e5ae8-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5ae8-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5ae8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5ae8-109">Requirements</span></span>  

 <span data-ttu-id="e5ae8-110">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="e5ae8-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ae8-111">참조</span><span class="sxs-lookup"><span data-stu-id="e5ae8-111">See also</span></span>

- [<span data-ttu-id="e5ae8-112">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5ae8-112">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="e5ae8-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5ae8-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="e5ae8-114">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5ae8-114">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="e5ae8-115">RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="e5ae8-115">RegisterNotifySource Method</span></span>](inotifyconnection2-registernotifysource-method.md)
