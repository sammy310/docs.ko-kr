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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ee186604529a3e77a0217c5688df5b62ff8b28c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736988"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="98d5f-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="98d5f-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="98d5f-103">현재 컴파일러는 CLR (공용 언어 런타임)를 사용 하 여 미리 컴파일된 올바른 플래그 설정을 가져옵니다 (즉, 네이티브)이이 프로세스에 로드 될 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="98d5f-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98d5f-104">구문</span><span class="sxs-lookup"><span data-stu-id="98d5f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98d5f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98d5f-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="98d5f-106">[out] 비트 조합에 대 한 포인터를 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) 로드할 올바른 미리 컴파일된 이미지를 선택 하는 데 사용 되는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98d5f-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98d5f-107">설명</span><span class="sxs-lookup"><span data-stu-id="98d5f-107">Remarks</span></span>  
 <span data-ttu-id="98d5f-108">사용 된 [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) CLR가 올바른 미리 컴파일된 이미지 로드를 선택 하는 데 사용할 플래그를 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="98d5f-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98d5f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98d5f-109">Requirements</span></span>  
 <span data-ttu-id="98d5f-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98d5f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98d5f-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98d5f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98d5f-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98d5f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98d5f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98d5f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
