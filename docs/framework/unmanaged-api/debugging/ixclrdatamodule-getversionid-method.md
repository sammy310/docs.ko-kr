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
ms.openlocfilehash: ff8ccf42d1131fb15d7473ae12ecefde9d55177f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395285"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="d7a3e-102">IXCLRDataModule:: GetVersionId 메서드</span><span class="sxs-lookup"><span data-stu-id="d7a3e-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="d7a3e-103">모듈의 버전 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7a3e-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d7a3e-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7a3e-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="d7a3e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7a3e-105">Parameters</span></span>

`vid`\
<span data-ttu-id="d7a3e-106">제한이 모듈의 버전 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a3e-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7a3e-107">설명</span><span class="sxs-lookup"><span data-stu-id="d7a3e-107">Remarks</span></span>

<span data-ttu-id="d7a3e-108">제공 된 메서드는 인터페이스의 일부 `IXCLRDataModule` 이며 가상 메서드 테이블의 4 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a3e-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7a3e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7a3e-109">Requirements</span></span>

<span data-ttu-id="d7a3e-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7a3e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d7a3e-111">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="d7a3e-111">**Header:** None</span></span>  
<span data-ttu-id="d7a3e-112">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="d7a3e-112">**Library:** None</span></span>  
<span data-ttu-id="d7a3e-113">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d7a3e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d7a3e-114">참조</span><span class="sxs-lookup"><span data-stu-id="d7a3e-114">See also</span></span>

- [<span data-ttu-id="d7a3e-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="d7a3e-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="d7a3e-116">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7a3e-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
