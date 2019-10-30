---
title: _AxlRSAKeyValueToPublicKeyToken 함수
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
ms.openlocfilehash: 1f53df33a65d3f75b7574eda3507e370c2e086ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099828"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="bff2b-102">\_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="bff2b-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="bff2b-103">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="bff2b-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bff2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="bff2b-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bff2b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bff2b-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="bff2b-106">진행 \<모듈러스 > 요소에서 base64로 인코딩된 모듈러스 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="bff2b-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="bff2b-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bff2b-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="bff2b-108">진행 \<지수가 > 요소에서 base64 인코딩된 지 수 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="bff2b-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="bff2b-109">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bff2b-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="bff2b-110">[out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR \*에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bff2b-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bff2b-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="bff2b-111">Return Value</span></span>  
 <span data-ttu-id="bff2b-112">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="bff2b-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="bff2b-113">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bff2b-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bff2b-114">참조</span><span class="sxs-lookup"><span data-stu-id="bff2b-114">See also</span></span>

- [<span data-ttu-id="bff2b-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="bff2b-115">Authenticode</span></span>](index.md)
