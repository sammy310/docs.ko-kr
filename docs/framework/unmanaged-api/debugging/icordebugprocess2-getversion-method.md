---
title: ICorDebugProcess2::GetVersion 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f3be81431201a4bb6011ea9b8f973061d3d101
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361237"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="3c7ab-102">ICorDebugProcess2::GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="3c7ab-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="3c7ab-103">이 프로세스에서 실행 중인 공용 언어 런타임 (CLR)의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3c7ab-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c7ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c7ab-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="3c7ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c7ab-105">Parameters</span></span>

`version`\
<span data-ttu-id="3c7ab-106">[out] 런타임의 버전 번호를 저장 하는 COR_VERSION 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3c7ab-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c7ab-107">설명</span><span class="sxs-lookup"><span data-stu-id="3c7ab-107">Remarks</span></span>

<span data-ttu-id="3c7ab-108">`GetVersion` 메서드는 런타임이 없습니다 프로세스에서 로드 된 경우 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c7ab-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c7ab-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c7ab-109">Requirements</span></span>

<span data-ttu-id="3c7ab-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c7ab-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="3c7ab-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c7ab-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="3c7ab-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c7ab-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3c7ab-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c7ab-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
