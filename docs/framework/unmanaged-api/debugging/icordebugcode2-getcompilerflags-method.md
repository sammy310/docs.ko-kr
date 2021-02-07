---
description: '자세히 알아보기: ICorDebugCode2:: GetCompilerFlags 메서드'
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
ms.openlocfilehash: 820b6d2392b2b91bbfc8a85b165c4d73a2546859
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711121"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="898eb-103">ICorDebugCode2::GetCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="898eb-103">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="898eb-104">이 코드 개체가 네이티브 이미지 생성기 (Ngen.exe)를 사용 하 여 컴파일 또는 생성 된 JIT (just-in-time) 인 조건을 지정 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="898eb-104">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="898eb-105">구문</span><span class="sxs-lookup"><span data-stu-id="898eb-105">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="898eb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="898eb-106">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="898eb-107">제한이 JIT 컴파일러 또는 네이티브 이미지 생성기의 동작을 지정 하는 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="898eb-107">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="898eb-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="898eb-108">Requirements</span></span>

<span data-ttu-id="898eb-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="898eb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="898eb-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="898eb-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="898eb-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="898eb-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="898eb-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="898eb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
