---
title: INotifySink2::OnSyncCallEnter 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5fc8b3e6432475468f1012313c95ddd2e22e026
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736264"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="87298-102">INotifySink2::OnSyncCallEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="87298-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="87298-103">호출을 시작 하면 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87298-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87298-104">구문</span><span class="sxs-lookup"><span data-stu-id="87298-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87298-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87298-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="87298-106">[in] 입력 한 호출의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="87298-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="87298-107">참조 [CALL_ID 구조체](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87298-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="87298-108">[in] 버퍼를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="87298-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="87298-109">[in] 호출 버퍼 바이트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="87298-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87298-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="87298-110">Return Value</span></span>  
 <span data-ttu-id="87298-111">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="87298-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87298-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87298-112">Requirements</span></span>  
 <span data-ttu-id="87298-113">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="87298-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87298-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="87298-114">See also</span></span>

- [<span data-ttu-id="87298-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87298-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="87298-116">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87298-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="87298-117">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87298-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
