---
description: '자세히 알아보기: GetHashFromBlob 함수'
title: GetHashFromBlob 함수
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
ms.openlocfilehash: dc5039e44440afa7a000bc61167faec0e5b6cc84
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736611"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="bb110-103">GetHashFromBlob 함수</span><span class="sxs-lookup"><span data-stu-id="bb110-103">GetHashFromBlob Function</span></span>

<span data-ttu-id="bb110-104">지정된 해시 알고리즘을 사용하여 지정된 메모리 주소에 있는 어셈블리의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-104">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="bb110-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-105">This function has been deprecated.</span></span> <span data-ttu-id="bb110-106">대신 [ICLRStrongName:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-106">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb110-107">구문</span><span class="sxs-lookup"><span data-stu-id="bb110-107">Syntax</span></span>

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a><span data-ttu-id="bb110-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bb110-108">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="bb110-109">진행 해시할 메모리 블록의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-109">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="bb110-110">진행 메모리 블록의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-110">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="bb110-111">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="bb110-112">기본 알고리즘에는 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-112">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="bb110-113">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-113">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="bb110-114">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-114">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="bb110-115">제한이 반환 된의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="bb110-115">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb110-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb110-116">Requirements</span></span>

<span data-ttu-id="bb110-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb110-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bb110-118">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="bb110-118">**Header:** StrongName.h</span></span>

<span data-ttu-id="bb110-119">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb110-119">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="bb110-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb110-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bb110-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb110-121">See also</span></span>

- [<span data-ttu-id="bb110-122">GetHashFromBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="bb110-122">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="bb110-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb110-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
