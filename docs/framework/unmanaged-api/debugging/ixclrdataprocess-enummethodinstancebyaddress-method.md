---
title: 'IXCLRDataProcess:: EnumMethodInstanceByAddress 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 142099ae5cf9637cc28e8c82aabcd831cc8f0f52
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420801"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="8c165-102">IXCLRDataProcess:: EnumMethodInstanceByAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="8c165-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="8c165-103">주소 오프셋에서 시작 하 여이 프로세스의 메서드 인스턴스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c165-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8c165-104">구문</span><span class="sxs-lookup"><span data-stu-id="8c165-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="8c165-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c165-105">Parameters</span></span>

`handle`\
<span data-ttu-id="8c165-106">진행 메서드 인스턴스를 열거 하는 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8c165-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="8c165-107">제한이 열거 된 메서드 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c165-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c165-108">설명</span><span class="sxs-lookup"><span data-stu-id="8c165-108">Remarks</span></span>

<span data-ttu-id="8c165-109">제공 된 메서드는 인터페이스의 일부 `IXCLRDataProcess` 이며 가상 메서드 테이블의 29 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c165-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c165-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c165-110">Requirements</span></span>

<span data-ttu-id="8c165-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c165-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="8c165-112">**헤더:** None **라이브러리:** 없음 **.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8c165-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8c165-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c165-113">See also</span></span>

- [<span data-ttu-id="8c165-114">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="8c165-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="8c165-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="8c165-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="8c165-116">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c165-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
