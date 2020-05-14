---
title: 'IXCLRDataModule:: Request 메서드'
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
ms.openlocfilehash: 44ee4fc7fc2368b65f6f2fffe6ac239beddc6293
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395262"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="a6e42-102">IXCLRDataModule:: Request 메서드</span><span class="sxs-lookup"><span data-stu-id="a6e42-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="a6e42-103">모듈의 데이터에 지정 된 버퍼를 채우도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a6e42-104">구문</span><span class="sxs-lookup"><span data-stu-id="a6e42-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="a6e42-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a6e42-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="a6e42-106">진행 보낼 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="a6e42-107">[in] 전달할 입력 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="a6e42-108">[in, size_is (inBufferSize)] 요청에서 보낼 원시 데이터에 대 한 버퍼 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="a6e42-109">진행 출력 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="a6e42-110">[out, size_is (outBufferSize)] 요청 응답을 저장 하는 데 사용 되는 버퍼 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6e42-111">설명</span><span class="sxs-lookup"><span data-stu-id="a6e42-111">Remarks</span></span>

<span data-ttu-id="a6e42-112">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataModule` 가상 메서드 테이블의 37th 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 37th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6e42-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6e42-113">Requirements</span></span>

<span data-ttu-id="a6e42-114">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6e42-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="a6e42-115">**헤더:** None **라이브러리:** 없음 **.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e42-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a6e42-116">참조</span><span class="sxs-lookup"><span data-stu-id="a6e42-116">See also</span></span>

- [<span data-ttu-id="a6e42-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="a6e42-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="a6e42-118">IXCLRDataModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6e42-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
