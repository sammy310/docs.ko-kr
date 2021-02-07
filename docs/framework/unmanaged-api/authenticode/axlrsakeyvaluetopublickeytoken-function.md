---
description: _AxlRSAKeyValueToPublicKeyToken 함수에 대해 자세히 알아보세요.
title: _AxlRSAKeyValueToPublicKeyToken 함수
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
topic_type:
- apiref
ms.openlocfilehash: 01fc4cdc1d9985375748307ca2d7fff97191c908
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747272"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="8f7ee-103">\_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="8f7ee-103">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="8f7ee-104">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f7ee-104">Converts a Modulus and Exponent to a strong name public key token.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f7ee-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f7ee-105">Syntax</span></span>

```cpp
HRESULT _AxlRSAKeyValueToPublicKeyToken (
    [in]  PCRYPT_DATA_BLOB pModulusBlob,
    [in]  PCRYPT_DATA_BLOB pExponentBlob,
    [out] LPWSTR           *ppwszPublicKeyToken
);
```

## <a name="parameters"></a><span data-ttu-id="8f7ee-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f7ee-106">Parameters</span></span>

 `pModulusBlob`\
 <span data-ttu-id="8f7ee-107">진행 A s e 64로 인코딩된 모듈러스 blob ( \<Modulus> 요소)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7ee-107">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="8f7ee-108">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f7ee-108">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

 `pExponentBlob`\
 <span data-ttu-id="8f7ee-109">진행 A s e 64로 인코딩된 지 수 blob ( \<Exponent> 요소)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7ee-109">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="8f7ee-110">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f7ee-110">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

 `ppwszPublicKeyToken`\
 <span data-ttu-id="8f7ee-111">[out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR \*에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7ee-111">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>

## <a name="return-value"></a><span data-ttu-id="8f7ee-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="8f7ee-112">Return Value</span></span>

 <span data-ttu-id="8f7ee-113">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="8f7ee-113">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="8f7ee-114">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f7ee-114">Otherwise, returns an error code.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f7ee-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f7ee-115">Requirements</span></span>

<span data-ttu-id="8f7ee-116">**어셈블리**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="8f7ee-116">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="8f7ee-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f7ee-117">See also</span></span>

- [<span data-ttu-id="8f7ee-118">Authenticode</span><span class="sxs-lookup"><span data-stu-id="8f7ee-118">Authenticode</span></span>](index.md)
