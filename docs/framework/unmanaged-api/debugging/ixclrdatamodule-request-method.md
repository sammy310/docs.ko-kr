---
title: IXCLRDataModule::Request 메서드
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 755063ca6da29a2e4733dd653306192ac0434ec0
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610602"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="6e8e0-102">IXCLRDataModule::Request 메서드</span><span class="sxs-lookup"><span data-stu-id="6e8e0-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="6e8e0-103">모듈의 데이터를 사용 하 여 지정 된 버퍼를 채우는 데 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8e0-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6e8e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e8e0-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="6e8e0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e8e0-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="6e8e0-106">[in] 요청 전송 하는 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8e0-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="6e8e0-107">[in]에 전달 되어야 하는 입력된 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8e0-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="6e8e0-108">[in, size_is(inBufferSize)] 요청에서 보낼 원시 데이터에 대 한 버퍼 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8e0-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="6e8e0-109">[in] 출력 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8e0-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="6e8e0-110">[out, size_is(outBufferSize)] 요청 응답을 저장 하는 데 버퍼 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8e0-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e8e0-111">설명</span><span class="sxs-lookup"><span data-stu-id="6e8e0-111">Remarks</span></span>

<span data-ttu-id="6e8e0-112">제공 된 메서드는의 일부는 `IXCLRDataModule` 인터페이스 및 가상 메서드 테이블의 36th 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8e0-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e8e0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e8e0-113">Requirements</span></span>

<span data-ttu-id="6e8e0-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e8e0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="6e8e0-115">**헤더:** None **라이브러리:** None **.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6e8e0-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6e8e0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e8e0-116">See also</span></span>

- [<span data-ttu-id="6e8e0-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="6e8e0-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="6e8e0-118">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e8e0-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)