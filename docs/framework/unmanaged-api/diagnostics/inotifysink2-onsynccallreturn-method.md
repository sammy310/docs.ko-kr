---
title: INotifySink2::OnSyncCallReturn 메서드
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae3067e6941451d4debd8d18ca58a91708a48e56
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487249"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="6c9e8-102">INotifySink2::OnSyncCallReturn 메서드</span><span class="sxs-lookup"><span data-stu-id="6c9e8-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="6c9e8-103">호출 반환 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c9e8-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c9e8-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c9e8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c9e8-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="6c9e8-106">[in] 반환 된 호출의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="6c9e8-107">참조 [CALL_ID 구조체](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="6c9e8-108">[in] 버퍼를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="6c9e8-109">[in] 호출 버퍼 바이트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c9e8-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="6c9e8-110">Return Value</span></span>  
 <span data-ttu-id="6c9e8-111">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9e8-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c9e8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c9e8-112">Requirements</span></span>  
 <span data-ttu-id="6c9e8-113">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="6c9e8-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c9e8-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c9e8-114">See also</span></span>
- [<span data-ttu-id="6c9e8-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c9e8-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="6c9e8-116">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c9e8-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="6c9e8-117">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c9e8-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
