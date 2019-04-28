---
title: IXCLRDataModule::GetVersionId 메서드
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
ms.openlocfilehash: e863f14676acc84f4d9f59d0898dee5b291bd30f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775442"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="6230f-102">IXCLRDataModule::GetVersionId 메서드</span><span class="sxs-lookup"><span data-stu-id="6230f-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="6230f-103">모듈의 버전 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6230f-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6230f-104">구문</span><span class="sxs-lookup"><span data-stu-id="6230f-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="6230f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6230f-105">Parameters</span></span>

`vid`\
<span data-ttu-id="6230f-106">[out] 모듈의 버전 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6230f-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="6230f-107">설명</span><span class="sxs-lookup"><span data-stu-id="6230f-107">Remarks</span></span>

<span data-ttu-id="6230f-108">제공 된 메서드는의 일부는 `IXCLRDataModule` 인터페이스 및 가상 메서드 테이블의 40 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6230f-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6230f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6230f-109">Requirements</span></span>

<span data-ttu-id="6230f-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6230f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6230f-111">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="6230f-111">**Header:** None</span></span>  
<span data-ttu-id="6230f-112">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="6230f-112">**Library:** None</span></span>  
<span data-ttu-id="6230f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6230f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6230f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6230f-114">See also</span></span>

- [<span data-ttu-id="6230f-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="6230f-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="6230f-116">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6230f-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)