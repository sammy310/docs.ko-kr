---
title: INotifyConnection2::RegisterNotifySource 메서드
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: 1286dd970e437af0a8b607ed050ab4838f73a41f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720050"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="d4fee-102">INotifyConnection2::RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="d4fee-102">INotifyConnection2::RegisterNotifySource Method</span></span>

<span data-ttu-id="d4fee-103">지정 된 알림 소스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4fee-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4fee-104">구문</span><span class="sxs-lookup"><span data-stu-id="d4fee-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4fee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4fee-105">Parameters</span></span>  

 `in_pNotifySource`  
 <span data-ttu-id="d4fee-106">진행 알림 소스로 사용할 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4fee-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="d4fee-107">제한이 알림 싱크로 사용할 개체를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fee-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4fee-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d4fee-108">Return Value</span></span>  

 <span data-ttu-id="d4fee-109">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4fee-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4fee-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4fee-110">Requirements</span></span>  

 <span data-ttu-id="d4fee-111">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="d4fee-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4fee-112">참조</span><span class="sxs-lookup"><span data-stu-id="d4fee-112">See also</span></span>

- [<span data-ttu-id="d4fee-113">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4fee-113">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="d4fee-114">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4fee-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="d4fee-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4fee-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="d4fee-116">UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="d4fee-116">UnregisterNotifySource Method</span></span>](inotifyconnection2-unregisternotifysource-method.md)
