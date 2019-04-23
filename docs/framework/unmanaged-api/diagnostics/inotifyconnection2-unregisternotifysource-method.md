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
ms.openlocfilehash: 742be1467d2f1e6eb7d8567ddf85f8e65ea4b8d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229461"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="cdd7a-102">INotifyConnection2::UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="cdd7a-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="cdd7a-103">연결에서 지정 된 알림 원본 개체를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7a-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdd7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="cdd7a-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdd7a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdd7a-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="cdd7a-106">[in] 알림 등록을 취소할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7a-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdd7a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="cdd7a-107">Return Value</span></span>  
 <span data-ttu-id="cdd7a-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7a-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdd7a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdd7a-109">Requirements</span></span>  
 <span data-ttu-id="cdd7a-110">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="cdd7a-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd7a-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="cdd7a-111">See also</span></span>

- [<span data-ttu-id="cdd7a-112">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdd7a-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="cdd7a-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdd7a-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="cdd7a-114">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdd7a-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="cdd7a-115">RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="cdd7a-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
