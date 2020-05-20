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
ms.openlocfilehash: 9d0fcdcd4fe1561f7565586e3327c6d3d7e0fe0a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442048"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="63574-102">INotifyConnection2::UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="63574-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="63574-103">지정 된 알림 소스 개체를 연결에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="63574-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63574-104">구문</span><span class="sxs-lookup"><span data-stu-id="63574-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63574-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63574-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="63574-106">진행 등록을 취소할 알림 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63574-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63574-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="63574-107">Return Value</span></span>  
 <span data-ttu-id="63574-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="63574-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63574-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63574-109">Requirements</span></span>  
 <span data-ttu-id="63574-110">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="63574-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63574-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63574-111">See also</span></span>

- [<span data-ttu-id="63574-112">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63574-112">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="63574-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63574-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="63574-114">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63574-114">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="63574-115">RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="63574-115">RegisterNotifySource Method</span></span>](inotifyconnection2-registernotifysource-method.md)
