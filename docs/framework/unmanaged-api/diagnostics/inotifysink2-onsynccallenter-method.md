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
ms.openlocfilehash: 57d12a463bc0904e1a5c873d24f843e004b95101
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720011"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="aa914-102">INotifySink2::OnSyncCallEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="aa914-102">INotifySink2::OnSyncCallEnter Method</span></span>

<span data-ttu-id="aa914-103">호출을 입력할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa914-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa914-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa914-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa914-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa914-105">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="aa914-106">진행 입력 하는 호출의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="aa914-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="aa914-107">[CALL_ID 구조체](call-id-structure.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa914-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="aa914-108">진행 버퍼를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa914-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="aa914-109">진행 호출 버퍼의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="aa914-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa914-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="aa914-110">Return Value</span></span>  

 <span data-ttu-id="aa914-111">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa914-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa914-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa914-112">Requirements</span></span>  

 <span data-ttu-id="aa914-113">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="aa914-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa914-114">참조</span><span class="sxs-lookup"><span data-stu-id="aa914-114">See also</span></span>

- [<span data-ttu-id="aa914-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa914-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="aa914-116">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa914-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="aa914-117">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa914-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
