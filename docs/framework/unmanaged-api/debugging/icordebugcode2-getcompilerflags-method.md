---
title: ICorDebugCode2::GetCompilerFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
ms.openlocfilehash: 4ad1fb1bcb43dda9796b54cbf868f89c001995da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777898"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="77f08-102">ICorDebugCode2::GetCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="77f08-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="77f08-103">네이티브 이미지 생성기 (Ngen.exe)를 사용 하 여이 코드 개체가 JIT (just-in-time) 컴파일 또는 생성 된 조건을 지정 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77f08-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="77f08-104">구문</span><span class="sxs-lookup"><span data-stu-id="77f08-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="77f08-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="77f08-105">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="77f08-106">제한이 JIT 컴파일러 또는 네이티브 이미지 생성기의 동작을 지정 하는 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="77f08-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="77f08-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77f08-107">Requirements</span></span>

<span data-ttu-id="77f08-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77f08-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="77f08-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77f08-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="77f08-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77f08-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="77f08-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77f08-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
