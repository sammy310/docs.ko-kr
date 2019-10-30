---
title: ICorDebugFunction::GetILCode 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
ms.openlocfilehash: c2ce4b95de75bef3928e144656b565676568caa0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137907"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="5271b-102">ICorDebugFunction::GetILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="5271b-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="5271b-103">이 ICorDebugFunction 개체와 연결 된 MSIL (Microsoft 중간 언어) 코드를 나타내는 ICorDebugCode 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5271b-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5271b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5271b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5271b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5271b-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="5271b-106">제한이 `ICorDebugCode` 인스턴스에 대 한 포인터 이거나, 함수가 MSIL로 컴파일되지 않은 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="5271b-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5271b-107">주의</span><span class="sxs-lookup"><span data-stu-id="5271b-107">Remarks</span></span>  
 <span data-ttu-id="5271b-108">이 함수에서 편집 하며 계속 하기가 허용 된 경우 `GetILCode` 메서드는 CLR (공용 언어 런타임)에서이 함수의 편집 된 코드 버전에 해당 하는 MSIL 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5271b-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5271b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5271b-109">Requirements</span></span>  
 <span data-ttu-id="5271b-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5271b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5271b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5271b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5271b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5271b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5271b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5271b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
