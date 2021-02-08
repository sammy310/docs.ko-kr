---
description: '자세히 알아보기: INotifySink2:: OnSyncCallOut 메서드'
title: INotifySink2::OnSyncCallOut 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
ms.openlocfilehash: 03028b138a7d95c618ae20530f66aa692d314cab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800242"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="e2b38-103">INotifySink2::OnSyncCallOut 메서드</span><span class="sxs-lookup"><span data-stu-id="e2b38-103">INotifySink2::OnSyncCallOut Method</span></span>

<span data-ttu-id="e2b38-104">호출이 호출 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2b38-104">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b38-105">구문</span><span class="sxs-lookup"><span data-stu-id="e2b38-105">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2b38-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e2b38-106">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="e2b38-107">진행 Out 호출의 ID입니다. [CALL_ID 구조체](call-id-structure.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2b38-107">[in] ID of the call that is out. See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="e2b38-108">제한이 버퍼를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2b38-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="e2b38-109">제한이 호출 버퍼의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="e2b38-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2b38-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="e2b38-110">Return Value</span></span>  

 <span data-ttu-id="e2b38-111">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2b38-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2b38-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2b38-112">Requirements</span></span>  

 <span data-ttu-id="e2b38-113">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="e2b38-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b38-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2b38-114">See also</span></span>

- [<span data-ttu-id="e2b38-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2b38-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="e2b38-116">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2b38-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="e2b38-117">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2b38-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
