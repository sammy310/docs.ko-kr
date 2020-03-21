---
title: IXCLR데이터 프로세스::에이엄메소드인스턴스바이트주소 방법
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
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176658"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="a118a-102">IXCLR데이터 프로세스::에이엄메소드인스턴스바이트주소 방법</span><span class="sxs-lookup"><span data-stu-id="a118a-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="a118a-103">주소 오프셋에서 시작하는 이 프로세스의 메서드 인스턴스를 모두보대해서는</span><span class="sxs-lookup"><span data-stu-id="a118a-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a118a-104">구문</span><span class="sxs-lookup"><span data-stu-id="a118a-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="a118a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a118a-105">Parameters</span></span>

`handle`\
<span data-ttu-id="a118a-106">【인】 메서드 인스턴스를 등록하기 위한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="a118a-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="a118a-107">【아웃】 수온이 있는 메서드 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="a118a-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="a118a-108">설명</span><span class="sxs-lookup"><span data-stu-id="a118a-108">Remarks</span></span>

<span data-ttu-id="a118a-109">제공된 메서드는 `IXCLRDataProcess` 인터페이스의 일부이며 가상 메서드 테이블의 28번째 슬롯에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a118a-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a118a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a118a-110">Requirements</span></span>

<span data-ttu-id="a118a-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a118a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="a118a-112">**헤더:** 없음 **라이브러리:** **없음 .NET 프레임워크 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a118a-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a118a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a118a-113">See also</span></span>

- [<span data-ttu-id="a118a-114">CLRDataSource유형 열거형</span><span class="sxs-lookup"><span data-stu-id="a118a-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a118a-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="a118a-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="a118a-116">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a118a-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
