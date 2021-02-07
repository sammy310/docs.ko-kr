---
description: _AxlGetIssuerPublicKeyHash 함수에 대해 자세히 알아보세요.
title: _AxlGetIssuerPublicKeyHash 함수
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
topic_type:
- apiref
ms.openlocfilehash: 586a072b33376a2fdade119fe3db0f48addfa3f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747363"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="a4df2-103">\_AxlGetIssuerPublicKeyHash 함수</span><span class="sxs-lookup"><span data-stu-id="a4df2-103">\_AxlGetIssuerPublicKeyHash Function</span></span>

<span data-ttu-id="a4df2-104">지정한 인증서에 서명하는 데 사용되는 프라이빗 키에 연결된 퍼블릭 키의 SHA-1 해시를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df2-104">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4df2-105">구문</span><span class="sxs-lookup"><span data-stu-id="a4df2-105">Syntax</span></span>

```cpp
HRESULT _AxlGetIssuerPublicKeyHash (
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,
    [out] LPWSTR                *ppwszPublicKeyHash
);
```

## <a name="parameters"></a><span data-ttu-id="a4df2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4df2-106">Parameters</span></span>

 `pChainContext`\
 <span data-ttu-id="a4df2-107">[in] CSP 공개 키 Blob입니다.</span><span class="sxs-lookup"><span data-stu-id="a4df2-107">[in] The CSP public key blob.</span></span> <span data-ttu-id="a4df2-108">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4df2-108">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

 `ppwszPublicKeyHash`\
 <span data-ttu-id="a4df2-109">[out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR \*에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4df2-109">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>

## <a name="return-value"></a><span data-ttu-id="a4df2-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="a4df2-110">Return Value</span></span>

 <span data-ttu-id="a4df2-111">함수가 정상적으로 실행되는 경우 `S_OK`이고 그렇지 않으면 `S_FALSE`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4df2-111">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>

## <a name="requirements"></a><span data-ttu-id="a4df2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4df2-112">Requirements</span></span>

<span data-ttu-id="a4df2-113">**어셈블리**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="a4df2-113">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="a4df2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4df2-114">See also</span></span>

- [<span data-ttu-id="a4df2-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="a4df2-115">Authenticode</span></span>](index.md)
