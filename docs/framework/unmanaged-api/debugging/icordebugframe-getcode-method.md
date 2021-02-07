---
description: '자세히 알아보기: ICorDebugFrame:: GetCode 메서드'
title: ICorDebugFrame::GetCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
ms.openlocfilehash: f45e0a29530a8b4ddbeaa92db4489a030ac1ae79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693033"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="fd60f-103">ICorDebugFrame::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="fd60f-103">ICorDebugFrame::GetCode Method</span></span>

<span data-ttu-id="fd60f-104">이 스택 프레임과 연결 된 코드에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd60f-104">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd60f-105">구문</span><span class="sxs-lookup"><span data-stu-id="fd60f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd60f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd60f-106">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="fd60f-107">제한이 이 프레임과 연결 된 코드를 나타내는 ICorDebugCode 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd60f-107">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd60f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd60f-108">Requirements</span></span>  

 <span data-ttu-id="fd60f-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd60f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd60f-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd60f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd60f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd60f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd60f-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd60f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
