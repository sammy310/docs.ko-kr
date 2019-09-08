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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 690035ffe0724d3987a198c78bf14e668527b98a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787027"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="50ace-102">\_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="50ace-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="50ace-103">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="50ace-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50ace-104">구문</span><span class="sxs-lookup"><span data-stu-id="50ace-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50ace-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50ace-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="50ace-106">진행 \<모듈러스 > 요소의 b a s e 64로 인코딩된 모듈러스 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="50ace-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="50ace-107">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="50ace-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="50ace-108">진행 \<지 수 > 요소에서 base64 인코딩된 지 수 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="50ace-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="50ace-109">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="50ace-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="50ace-110">[out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR \*에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="50ace-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50ace-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="50ace-111">Return Value</span></span>  
 <span data-ttu-id="50ace-112">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="50ace-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="50ace-113">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ace-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50ace-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="50ace-114">See also</span></span>

- [<span data-ttu-id="50ace-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="50ace-115">Authenticode</span></span>](index.md)
