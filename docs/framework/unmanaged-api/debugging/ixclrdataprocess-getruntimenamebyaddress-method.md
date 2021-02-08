---
description: '자세히 알아보기: IXCLRDataProcess:: GetRuntimeNameByAddress 메서드'
title: 'IXCLRDataProcess:: Getrunti Amebyaddress 메서드'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 62d9ae73c216748cc8eb02aedd41cf19f475d071
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800658"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a><span data-ttu-id="b9698-103">IXCLRDataProcess:: Getrunti Amebyaddress 메서드</span><span class="sxs-lookup"><span data-stu-id="b9698-103">IXCLRDataProcess::GetRuntimeNameByAddress Method</span></span>

<span data-ttu-id="b9698-104">지정 된 주소에 대 한 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b9698-104">Gets a name for the given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b9698-105">구문</span><span class="sxs-lookup"><span data-stu-id="b9698-105">Syntax</span></span>

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a><span data-ttu-id="b9698-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9698-106">Parameters</span></span>

`address`\
<span data-ttu-id="b9698-107">진행 `CLRDATA_ADDRESS` 코드 주소를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9698-107">[in] A `CLRDATA_ADDRESS` value that represents a code address.</span></span>

`flags`\
<span data-ttu-id="b9698-108">진행 ' 0 '으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9698-108">[in] Set to '0'.</span></span>

`bufLen`\
<span data-ttu-id="b9698-109">진행 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="b9698-109">[in] The length of the buffer.</span></span>

`namLen`\
<span data-ttu-id="b9698-110">제한이 반환 된 문자 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b9698-110">[out] A pointer to the number of characters returned.</span></span>

`namBuf`\
<span data-ttu-id="b9698-111">[out, size_is ( `bufLen` )] `bufLen` 런타임 이름을 저장 하는 길이의 입력 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b9698-111">[out, size_is(`bufLen`)] The input buffer of length `bufLen` that stores the runtime name.</span></span>

`displacement`\
<span data-ttu-id="b9698-112">제한이 `CLRDATA_ADDRESS` 반환 된 기호의 코드 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b9698-112">[out] A `CLRDATA_ADDRESS` pointer to the code offset of the returned symbol.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9698-113">설명</span><span class="sxs-lookup"><span data-stu-id="b9698-113">Remarks</span></span>

<span data-ttu-id="b9698-114">제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataProcess` 가상 메서드 테이블의 16 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9698-114">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 16th slot of the virtual-method table.</span></span>

> [!NOTE]
> <span data-ttu-id="b9698-115">버퍼가 이름에 대해 충분히 크지 않은 경우이 메서드는를 반환 하 `S_FALSE` 고 `nameLen` 를 필요한 버퍼 길이로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9698-115">If the buffer is not large enough for the name, this method returns `S_FALSE` and sets `nameLen` to the required buffer length.</span></span>

## <a name="requirements"></a><span data-ttu-id="b9698-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9698-116">Requirements</span></span>

<span data-ttu-id="b9698-117">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9698-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="b9698-118">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="b9698-118">**Header:** None\</span></span>
<span data-ttu-id="b9698-119">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="b9698-119">**Library:** None\</span></span>
<span data-ttu-id="b9698-120">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b9698-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b9698-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9698-121">See also</span></span>

- [<span data-ttu-id="b9698-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="b9698-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="b9698-123">IXCLRDataProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9698-123">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
