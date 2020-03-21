---
title: StrongNameTokenFromPublicKey 함수
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175059"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="ff327-102">StrongNameTokenFromPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="ff327-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="ff327-103">공개 키를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-103">Gets a token representing a public key.</span></span> <span data-ttu-id="ff327-104">강력한 이름 토큰은 공개 키의 단축된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="ff327-105">이 함수는 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-105">This function has been deprecated.</span></span> <span data-ttu-id="ff327-106">대신 [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff327-107">구문</span><span class="sxs-lookup"><span data-stu-id="ff327-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff327-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff327-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="ff327-109">【인】 강력한 이름 서명을 생성하는 데 사용되는 키 쌍의 공용 부분을 포함하는 [PublicKeyBlob](publickeyblob-structure.md) 형식의 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="ff327-110">【인】 의 크기(바이트)입니다. `pbPublicKeyBlob`</span><span class="sxs-lookup"><span data-stu-id="ff327-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="ff327-111">【아웃】 에 전달된 키에 해당하는 `pbPublicKeyBlob`강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="ff327-112">공통 언어 런타임은 토큰을 반환할 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="ff327-113">호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용하여 이 메모리를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="ff327-114">【아웃】 반환된 강력한 이름 토큰의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff327-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="ff327-115">Return Value</span></span>  
 <span data-ttu-id="ff327-116">`true`성공적인 완료시; 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="ff327-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff327-117">설명</span><span class="sxs-lookup"><span data-stu-id="ff327-117">Remarks</span></span>  
 <span data-ttu-id="ff327-118">강력한 이름 토큰은 메타데이터에 키 정보를 저장할 때 공간을 절약하는 데 사용되는 공개 키의 단축된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="ff327-119">특히 강력한 이름 토큰은 종속 어셈블리를 참조하기 위해 어셈블리 참조에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="ff327-120">`StrongNameTokenFromPublicKey`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ff327-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff327-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff327-121">Requirements</span></span>  
 <span data-ttu-id="ff327-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff327-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff327-123">**헤더:** 스트롱네임</span><span class="sxs-lookup"><span data-stu-id="ff327-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ff327-124">**라이브러리:** mscoree.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ff327-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="ff327-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff327-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff327-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff327-126">See also</span></span>

- [<span data-ttu-id="ff327-127">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="ff327-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="ff327-128">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="ff327-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="ff327-129">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="ff327-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
