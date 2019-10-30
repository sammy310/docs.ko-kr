---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: 2d5b07acb9dc374fdd8872ed982a92171da28603
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137228"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="2dccd-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="2dccd-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="2dccd-103">CLR (공용 언어 런타임)이이 프로세스에 로드할 올바른 미리 컴파일된 (즉, 네이티브) 이미지를 선택 하는 데 사용 하는 현재 컴파일러 플래그 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2dccd-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dccd-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dccd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dccd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dccd-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="2dccd-106">제한이 로드할 올바른 미리 컴파일된 이미지를 선택 하는 데 사용 되는 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) 열거형 값의 비트 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2dccd-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dccd-107">주의</span><span class="sxs-lookup"><span data-stu-id="2dccd-107">Remarks</span></span>  
 <span data-ttu-id="2dccd-108">[ICorDebugProcess2:: SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) 메서드를 사용 하 여 CLR이 로드할 올바른 미리 컴파일된 이미지를 선택 하는 데 사용할 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dccd-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dccd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dccd-109">Requirements</span></span>  
 <span data-ttu-id="2dccd-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dccd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dccd-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2dccd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2dccd-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dccd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dccd-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dccd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
