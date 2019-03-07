---
title: IXCLRDataProcess::EnumMethodInstanceByAddress 메서드
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
ms.openlocfilehash: 23b567e4119578fba2f8cd4ba47f66dcf56a3878
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496848"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="4818b-102">IXCLRDataProcess::EnumMethodInstanceByAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="4818b-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="4818b-103">메서드 인스턴스의 주소 오프셋에서 시작 하는이 프로세스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4818b-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4818b-104">구문</span><span class="sxs-lookup"><span data-stu-id="4818b-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="4818b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4818b-105">Parameters</span></span>

`handle`\
<span data-ttu-id="4818b-106">[in] 메서드 인스턴스를 열거 하는 것에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="4818b-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="4818b-107">[out] 열거형된 메서드 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="4818b-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="4818b-108">설명</span><span class="sxs-lookup"><span data-stu-id="4818b-108">Remarks</span></span>

<span data-ttu-id="4818b-109">제공 된 메서드는의 일부는 `IXCLRDataProcess` 인터페이스 및 가상 메서드 테이블의 28 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4818b-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4818b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4818b-110">Requirements</span></span>

<span data-ttu-id="4818b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4818b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="4818b-112">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="4818b-112">**Header:** None</span></span>   
<span data-ttu-id="4818b-113">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="4818b-113">**Library:** None</span></span>   
<span data-ttu-id="4818b-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4818b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="4818b-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="4818b-115">See also</span></span>
- [<span data-ttu-id="4818b-116">CLRDataSourceType 열거형</span><span class="sxs-lookup"><span data-stu-id="4818b-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="4818b-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="4818b-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="4818b-118">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4818b-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
