---
title: 'IXCLRDataProcess:: StartEnumMethodInstancesByAddress 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e28fa73300e147ac07a2d325fbf517480bb73797
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394942"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="3c848-102">IXCLRDataProcess:: StartEnumMethodInstancesByAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="3c848-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="3c848-103">지정 된 주소에서 시작 하는의 메서드 인스턴스를 열거 하는 핸들을 제공 합니다 `AppDomain` .</span><span class="sxs-lookup"><span data-stu-id="3c848-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3c848-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c848-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="3c848-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c848-105">Parameters</span></span>

`address`\
<span data-ttu-id="3c848-106">진행 첫 번째 메서드 인스턴스의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3c848-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="3c848-107">진행 메서드 인스턴스의 AppDomain입니다.</span><span class="sxs-lookup"><span data-stu-id="3c848-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="3c848-108">제한이 메서드 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="3c848-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c848-109">설명</span><span class="sxs-lookup"><span data-stu-id="3c848-109">Remarks</span></span>

<span data-ttu-id="3c848-110">제공 된 메서드는 인터페이스의 일부 `IXCLRDataProcess` 이며 가상 메서드 테이블의 28 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c848-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c848-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c848-111">Requirements</span></span>

<span data-ttu-id="3c848-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c848-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3c848-113">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="3c848-113">**Header:** None</span></span>  
<span data-ttu-id="3c848-114">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="3c848-114">**Library:** None</span></span>  
<span data-ttu-id="3c848-115">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3c848-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3c848-116">참조</span><span class="sxs-lookup"><span data-stu-id="3c848-116">See also</span></span>

- [<span data-ttu-id="3c848-117">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="3c848-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3c848-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="3c848-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="3c848-119">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c848-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
