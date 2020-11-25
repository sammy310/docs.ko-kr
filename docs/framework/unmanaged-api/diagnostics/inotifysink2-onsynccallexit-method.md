---
title: INotifySink2::OnSyncCallExit 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
ms.openlocfilehash: 9049cd42e9c10cdcff62b005094b56c9df9ce975
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719998"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="d218d-102">INotifySink2::OnSyncCallExit 메서드</span><span class="sxs-lookup"><span data-stu-id="d218d-102">INotifySink2::OnSyncCallExit Method</span></span>

<span data-ttu-id="d218d-103">호출을 종료할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d218d-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d218d-104">구문</span><span class="sxs-lookup"><span data-stu-id="d218d-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d218d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d218d-105">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="d218d-106">진행 종료 되는 호출의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d218d-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="d218d-107">[CALL_ID 구조체](call-id-structure.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d218d-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="d218d-108">제한이 버퍼를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d218d-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="d218d-109">제한이 호출 버퍼의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d218d-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d218d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="d218d-110">Return Value</span></span>  

 <span data-ttu-id="d218d-111">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="d218d-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d218d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d218d-112">Requirements</span></span>  

 <span data-ttu-id="d218d-113">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="d218d-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d218d-114">참조</span><span class="sxs-lookup"><span data-stu-id="d218d-114">See also</span></span>

- [<span data-ttu-id="d218d-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d218d-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="d218d-116">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d218d-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="d218d-117">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d218d-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
