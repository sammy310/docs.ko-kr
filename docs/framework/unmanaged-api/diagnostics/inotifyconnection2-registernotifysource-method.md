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
ms.openlocfilehash: b7fa777466e2c7edd7b3110dd91e776785c63c58
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442074"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="c12b9-102">INotifyConnection2::RegisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="c12b9-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="c12b9-103">지정 된 알림 소스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b9-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c12b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="c12b9-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c12b9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c12b9-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="c12b9-106">진행 알림 소스로 사용할 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b9-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="c12b9-107">제한이 알림 싱크로 사용할 개체를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c12b9-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c12b9-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="c12b9-108">Return Value</span></span>  
 <span data-ttu-id="c12b9-109">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="c12b9-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c12b9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c12b9-110">Requirements</span></span>  
 <span data-ttu-id="c12b9-111">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="c12b9-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12b9-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c12b9-112">See also</span></span>

- [<span data-ttu-id="c12b9-113">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c12b9-113">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="c12b9-114">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c12b9-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="c12b9-115">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c12b9-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="c12b9-116">UnregisterNotifySource 메서드</span><span class="sxs-lookup"><span data-stu-id="c12b9-116">UnregisterNotifySource Method</span></span>](inotifyconnection2-unregisternotifysource-method.md)
