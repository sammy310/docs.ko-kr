---
description: '자세히 알아보기: ICorDebugThread:: GetObject 메서드'
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
ms.openlocfilehash: db5760be0ef4230b2dccec9d1836ea0eee56f231
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658958"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="ad102-103">ICorDebugThread::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="ad102-103">ICorDebugThread::GetObject Method</span></span>

<span data-ttu-id="ad102-104">CLR (공용 언어 런타임) 스레드에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad102-104">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad102-105">구문</span><span class="sxs-lookup"><span data-stu-id="ad102-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad102-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad102-106">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="ad102-107">제한이 CLR 스레드를 나타내는 ICorDebugValue 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ad102-107">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad102-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad102-108">Requirements</span></span>  

 <span data-ttu-id="ad102-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad102-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad102-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad102-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad102-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad102-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad102-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad102-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad102-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad102-113">See also</span></span>

- <xref:System.Threading.Thread>
