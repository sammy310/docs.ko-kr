---
title: _AxlPublicKeyBlobToPublicKeyToken 함수
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b2535441da173ee13653c68f25039fd1431261a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147435"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="e9ce7-102">_AxlPublicKeyBlobToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="e9ce7-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="e9ce7-103">CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e9ce7-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9ce7-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9ce7-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9ce7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9ce7-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="e9ce7-106">[in] CSP 공개 키 Blob입니다.</span><span class="sxs-lookup"><span data-stu-id="e9ce7-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="e9ce7-107">[out] 16진수로 인코딩된 공개 키 해시를 받는 WCHAR \*에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e9ce7-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9ce7-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="e9ce7-108">Return Value</span></span>  
 <span data-ttu-id="e9ce7-109">함수가 정상적으로 실행되는 경우 `S_OK`이고 그렇지 않으면 `S_FALSE`입니다.</span><span class="sxs-lookup"><span data-stu-id="e9ce7-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ce7-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="e9ce7-110">See also</span></span>

- [<span data-ttu-id="e9ce7-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e9ce7-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
