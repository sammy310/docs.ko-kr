---
title: ICorDebugThread::GetObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
ms.openlocfilehash: 5cb95fb7cf70dbf7616e9bc59ebf44de090de883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133441"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="6d0d1-102">ICorDebugThread::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="6d0d1-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="6d0d1-103">CLR (공용 언어 런타임) 스레드에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d0d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d0d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d0d1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d0d1-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="6d0d1-106">제한이 CLR 스레드를 나타내는 ICorDebugValue 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d0d1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d0d1-107">Requirements</span></span>  
 <span data-ttu-id="6d0d1-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d0d1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d0d1-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d0d1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d0d1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d0d1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d0d1-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d0d1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d0d1-112">참조</span><span class="sxs-lookup"><span data-stu-id="6d0d1-112">See also</span></span>

- <xref:System.Threading.Thread>
