---
title: 'IXCLRDataModule:: GetVersionId 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetVersionId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetVersionId Method
helpviewer.keywords:
- IXCLRDataModule::GetVersionId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9d5ef137a5d76c3d7545ab16921352123e978fb1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420866"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="7ae9c-102">IXCLRDataModule:: GetVersionId 메서드</span><span class="sxs-lookup"><span data-stu-id="7ae9c-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="7ae9c-103">모듈의 버전 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ae9c-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="7ae9c-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ae9c-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="7ae9c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ae9c-105">Parameters</span></span>

`vid`\
<span data-ttu-id="7ae9c-106">제한이 모듈의 버전 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7ae9c-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ae9c-107">설명</span><span class="sxs-lookup"><span data-stu-id="7ae9c-107">Remarks</span></span>

<span data-ttu-id="7ae9c-108">제공 된 메서드는 인터페이스의 일부 `IXCLRDataModule` 이며 가상 메서드 테이블의 4 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ae9c-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ae9c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ae9c-109">Requirements</span></span>

<span data-ttu-id="7ae9c-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ae9c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="7ae9c-111">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="7ae9c-111">**Header:** None</span></span>  
<span data-ttu-id="7ae9c-112">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="7ae9c-112">**Library:** None</span></span>  
<span data-ttu-id="7ae9c-113">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7ae9c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7ae9c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ae9c-114">See also</span></span>

- [<span data-ttu-id="7ae9c-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="7ae9c-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="7ae9c-116">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ae9c-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
