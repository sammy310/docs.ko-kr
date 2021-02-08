---
description: '자세히 알아보기: INotifyConnection2:: RegisterNotifySource 메서드'
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
ms.openlocfilehash: 97aacf7f2005a1e9f21acebd6c5f5ed65867b245
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800320"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="68849-103">INotifyConnection2::RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="68849-103">INotifyConnection2::RegisterNotifySource Method</span></span>

<span data-ttu-id="68849-104">지정 된 알림 소스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="68849-104">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68849-105">구문</span><span class="sxs-lookup"><span data-stu-id="68849-105">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68849-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68849-106">Parameters</span></span>  

 `in_pNotifySource`  
 <span data-ttu-id="68849-107">진행 알림 소스로 사용할 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68849-107">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="68849-108">제한이 알림 싱크로 사용할 개체를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="68849-108">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68849-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="68849-109">Return Value</span></span>  

 <span data-ttu-id="68849-110">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="68849-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68849-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68849-111">Requirements</span></span>  

 <span data-ttu-id="68849-112">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="68849-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68849-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68849-113">See also</span></span>

- [<span data-ttu-id="68849-114">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68849-114">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="68849-115">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68849-115">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="68849-116">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68849-116">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="68849-117">UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="68849-117">UnregisterNotifySource Method</span></span>](inotifyconnection2-unregisternotifysource-method.md)
