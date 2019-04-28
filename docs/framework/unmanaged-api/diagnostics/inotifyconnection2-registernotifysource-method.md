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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9dac5ae2f0f77c7b6d2dbd7f908f3552823735b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940428"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="29b15-102">INotifyConnection2::RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="29b15-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="29b15-103">지정 된 알림 소스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="29b15-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29b15-104">구문</span><span class="sxs-lookup"><span data-stu-id="29b15-104">Syntax</span></span>  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29b15-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29b15-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="29b15-106">[in] 알림 소스로 사용할 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b15-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="29b15-107">[out] 알림 싱크로 사용할 개체를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="29b15-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29b15-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="29b15-108">Return Value</span></span>  
 <span data-ttu-id="29b15-109">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="29b15-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29b15-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29b15-110">Requirements</span></span>  
 <span data-ttu-id="29b15-111">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="29b15-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b15-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="29b15-112">See also</span></span>

- [<span data-ttu-id="29b15-113">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29b15-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="29b15-114">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29b15-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="29b15-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29b15-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="29b15-116">UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="29b15-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
