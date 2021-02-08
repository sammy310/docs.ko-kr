---
description: _AxlPublicKeyBlobToPublicKeyToken 함수에 대해 자세히 알아보세요.
title: _AxlPublicKeyBlobToPublicKeyToken 함수
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
topic_type:
- apiref
ms.openlocfilehash: df0b484bad64051eb892d4898a6c90777cc2d5cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781937"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="e19a4-103">\_AxlPublicKeyBlobToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="e19a4-103">\_AxlPublicKeyBlobToPublicKeyToken Function</span></span>

<span data-ttu-id="e19a4-104">CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e19a4-104">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>

## <a name="syntax"></a><span data-ttu-id="e19a4-105">구문</span><span class="sxs-lookup"><span data-stu-id="e19a4-105">Syntax</span></span>

```cpp
HRESULT _AxlPublicKeyBlobToPublicKeyToken (
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,
    [out] LPWSTR                 *ppwszPublicKeyToken
);
```

## <a name="parameters"></a><span data-ttu-id="e19a4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e19a4-106">Parameters</span></span>

 `pCspPublicKeyBlob`\
 <span data-ttu-id="e19a4-107">[in] CSP 공개 키 Blob입니다.</span><span class="sxs-lookup"><span data-stu-id="e19a4-107">[in] The CSP public key blob.</span></span>

 `ppwszPublicKeyHash`\
 <span data-ttu-id="e19a4-108">[out] 16진수로 인코딩된 공개 키 해시를 받는 WCHAR \*에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e19a4-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>

## <a name="return-value"></a><span data-ttu-id="e19a4-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="e19a4-109">Return Value</span></span>

 <span data-ttu-id="e19a4-110">함수가 정상적으로 실행되는 경우 `S_OK`이고 그렇지 않으면 `S_FALSE`입니다.</span><span class="sxs-lookup"><span data-stu-id="e19a4-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>

## <a name="requirements"></a><span data-ttu-id="e19a4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e19a4-111">Requirements</span></span>

<span data-ttu-id="e19a4-112">**어셈블리**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="e19a4-112">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="e19a4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e19a4-113">See also</span></span>

- [<span data-ttu-id="e19a4-114">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e19a4-114">Authenticode</span></span>](index.md)
