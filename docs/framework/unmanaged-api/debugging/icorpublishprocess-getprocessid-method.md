---
description: '자세히 알아보기: ICorPublishProcess:: GetProcessID 메서드'
title: ICorPublishProcess::GetProcessID 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: f959a49330e0ef4ade2a878acfd287657b5086ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728823"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="25704-103">ICorPublishProcess::GetProcessID 메서드</span><span class="sxs-lookup"><span data-stu-id="25704-103">ICorPublishProcess::GetProcessID Method</span></span>

<span data-ttu-id="25704-104">이 프로세스에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="25704-104">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25704-105">구문</span><span class="sxs-lookup"><span data-stu-id="25704-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25704-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25704-106">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="25704-107">제한이 이 [ICorPublishProcess](icorpublishprocess-interface.md) 개체가 나타내는 프로세스의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="25704-107">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25704-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25704-108">Requirements</span></span>  

 <span data-ttu-id="25704-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25704-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25704-110">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="25704-110">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="25704-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25704-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25704-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25704-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25704-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25704-113">See also</span></span>

- [<span data-ttu-id="25704-114">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25704-114">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
