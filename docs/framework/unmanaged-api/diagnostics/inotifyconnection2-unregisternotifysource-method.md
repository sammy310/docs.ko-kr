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
ms.openlocfilehash: cf399d0c7dec7528f02988ddfe6ca5c0b1f0c4c3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440989"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="d4ad6-102">INotifyConnection2::UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="d4ad6-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="d4ad6-103">지정 된 알림 소스 개체를 연결에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ad6-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4ad6-104">구문</span><span class="sxs-lookup"><span data-stu-id="d4ad6-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4ad6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4ad6-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="d4ad6-106">진행 등록을 취소할 알림 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4ad6-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4ad6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d4ad6-107">Return Value</span></span>  
 <span data-ttu-id="d4ad6-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ad6-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4ad6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4ad6-109">Requirements</span></span>  
 <span data-ttu-id="d4ad6-110">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="d4ad6-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ad6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4ad6-111">See also</span></span>

- [<span data-ttu-id="d4ad6-112">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4ad6-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="d4ad6-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4ad6-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="d4ad6-114">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4ad6-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="d4ad6-115">RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="d4ad6-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
