---
description: '자세히 알아보기: IXCLRDataProcess:: EndEnumMethodInstancesByAddress 메서드'
title: 'IXCLRDataProcess:: EndEnumMethodInstancesByAddress 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 2e01fe0737319a7b336d9f6992bf81b2c57f9e70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800723"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="67054-103">IXCLRDataProcess:: EndEnumMethodInstancesByAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="67054-103">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="67054-104">인스턴스 열거 중 사용 되는 내부 반복기에서 사용 하는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="67054-104">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="67054-105">구문</span><span class="sxs-lookup"><span data-stu-id="67054-105">Syntax</span></span>

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="67054-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="67054-106">Parameters</span></span>

`handle`\
<span data-ttu-id="67054-107">제한이 메서드 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="67054-107">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="67054-108">설명</span><span class="sxs-lookup"><span data-stu-id="67054-108">Remarks</span></span>

<span data-ttu-id="67054-109">제공 된 메서드는 인터페이스의 일부 `IXCLRDataProcess` 이며 가상 메서드 테이블의 30 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="67054-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 30th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="67054-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67054-110">Requirements</span></span>

<span data-ttu-id="67054-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67054-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="67054-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="67054-112">**Header:** None</span></span>  
<span data-ttu-id="67054-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="67054-113">**Library:** None</span></span>  
<span data-ttu-id="67054-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="67054-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="67054-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67054-115">See also</span></span>

- [<span data-ttu-id="67054-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="67054-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="67054-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="67054-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="67054-118">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67054-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
