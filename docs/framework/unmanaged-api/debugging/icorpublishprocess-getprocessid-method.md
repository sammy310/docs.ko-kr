---
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
ms.openlocfilehash: 4cc6bbde2c7367c1109ca73e66f2670a56b2cdbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790550"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="5a504-102">ICorPublishProcess::GetProcessID 메서드</span><span class="sxs-lookup"><span data-stu-id="5a504-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="5a504-103">이 프로세스에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a504-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a504-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a504-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a504-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a504-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="5a504-106">제한이 이 [ICorPublishProcess](icorpublishprocess-interface.md) 개체가 나타내는 프로세스의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5a504-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a504-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a504-107">Requirements</span></span>  
 <span data-ttu-id="5a504-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a504-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a504-109">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="5a504-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5a504-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a504-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a504-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a504-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a504-112">참조</span><span class="sxs-lookup"><span data-stu-id="5a504-112">See also</span></span>

- [<span data-ttu-id="5a504-113">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a504-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
