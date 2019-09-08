---
title: _AxlGetIssuerPublicKeyHash 함수
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b101a912eb58ed14f81d847ea2fd6ce9f22c065
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787094"
---
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="ad21e-102">\_AxlGetIssuerPublicKeyHash 함수</span><span class="sxs-lookup"><span data-stu-id="ad21e-102">\_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="ad21e-103">지정한 인증서에 서명하는 데 사용되는 프라이빗 키에 연결된 퍼블릭 키의 SHA-1 해시를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ad21e-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad21e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad21e-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad21e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad21e-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="ad21e-106">[in] CSP 공개 키 Blob입니다.</span><span class="sxs-lookup"><span data-stu-id="ad21e-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="ad21e-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad21e-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="ad21e-108">[out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR \*에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ad21e-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad21e-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ad21e-109">Return Value</span></span>  
 <span data-ttu-id="ad21e-110">함수가 정상적으로 실행되는 경우 `S_OK`이고 그렇지 않으면 `S_FALSE`입니다.</span><span class="sxs-lookup"><span data-stu-id="ad21e-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad21e-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad21e-111">See also</span></span>

- [<span data-ttu-id="ad21e-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="ad21e-112">Authenticode</span></span>](index.md)
