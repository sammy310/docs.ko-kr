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
ms.openlocfilehash: 5c1e2bfc7fd55e807af68744e28faa473daea772
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674218"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="04cd5-102">\_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="04cd5-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="04cd5-103">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="04cd5-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04cd5-104">구문</span><span class="sxs-lookup"><span data-stu-id="04cd5-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04cd5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04cd5-105">Parameters</span></span>  

 `pModulusBlob`  
 <span data-ttu-id="04cd5-106">진행 A s e 64로 인코딩된 모듈러스 blob ( \<Modulus> 요소)입니다.</span><span class="sxs-lookup"><span data-stu-id="04cd5-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="04cd5-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04cd5-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="04cd5-108">진행 A s e 64로 인코딩된 지 수 blob ( \<Exponent> 요소)입니다.</span><span class="sxs-lookup"><span data-stu-id="04cd5-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="04cd5-109">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04cd5-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="04cd5-110">[out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR \*에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="04cd5-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04cd5-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="04cd5-111">Return Value</span></span>  

 <span data-ttu-id="04cd5-112">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="04cd5-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="04cd5-113">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="04cd5-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04cd5-114">참조</span><span class="sxs-lookup"><span data-stu-id="04cd5-114">See also</span></span>

- [<span data-ttu-id="04cd5-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="04cd5-115">Authenticode</span></span>](index.md)
