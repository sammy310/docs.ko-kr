---
title: ICorDebugModule::GetSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 4f9818137016dc3e0522ed516c52df2550ffdfca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212518"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="5f2b9-102">ICorDebugModule::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="5f2b9-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="5f2b9-103">모듈의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f2b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f2b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f2b9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f2b9-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="5f2b9-106">제한이 모듈의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="5f2b9-107">모듈이 네이티브 이미지 생성기 (Ngen.exe)에서 생성 된 경우 모듈의 크기는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f2b9-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f2b9-108">Requirements</span></span>  
 <span data-ttu-id="5f2b9-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f2b9-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f2b9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f2b9-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f2b9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f2b9-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f2b9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
