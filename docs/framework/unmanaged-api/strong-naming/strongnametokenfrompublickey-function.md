---
description: '자세히 알아보기: StrongNameTokenFromPublicKey 함수'
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
ms.openlocfilehash: f978c9b2727db4b293b9c92a8789fbf9ba749d41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636284"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="48161-103">StrongNameTokenFromPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="48161-103">StrongNameTokenFromPublicKey Function</span></span>

<span data-ttu-id="48161-104">공개 키를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="48161-104">Gets a token representing a public key.</span></span> <span data-ttu-id="48161-105">강력한 이름 토큰은 공개 키의 축약 된 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="48161-105">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="48161-106">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48161-106">This function has been deprecated.</span></span> <span data-ttu-id="48161-107">대신 [ICLRStrongName:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48161-107">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48161-108">구문</span><span class="sxs-lookup"><span data-stu-id="48161-108">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48161-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48161-109">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="48161-110">진행 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 [PublicKeyBlob](publickeyblob-structure.md) 형식의 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="48161-110">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="48161-111">진행 의 크기 (바이트)입니다 `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="48161-111">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="48161-112">제한이 전달 된 키에 해당 하는 강력한 이름 토큰 `pbPublicKeyBlob` 입니다.</span><span class="sxs-lookup"><span data-stu-id="48161-112">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="48161-113">공용 언어 런타임은 토큰을 반환할 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="48161-113">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="48161-114">호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용 하 여이 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48161-114">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="48161-115">제한이 반환 된 강력한 이름 토큰의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="48161-115">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48161-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="48161-116">Return Value</span></span>  

 <span data-ttu-id="48161-117">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="48161-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48161-118">설명</span><span class="sxs-lookup"><span data-stu-id="48161-118">Remarks</span></span>  

 <span data-ttu-id="48161-119">강력한 이름 토큰은 키 정보를 메타 데이터에 저장할 때 공간을 절약 하는 데 사용 되는 공개 키의 축약 된 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="48161-119">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="48161-120">특히 강력한 이름 토큰은 어셈블리 참조에서 종속 어셈블리를 참조 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48161-120">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="48161-121">`StrongNameTokenFromPublicKey`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="48161-121">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48161-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48161-122">Requirements</span></span>  

 <span data-ttu-id="48161-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48161-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48161-124">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="48161-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="48161-125">**라이브러리:** mscoree.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48161-125">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="48161-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48161-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48161-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48161-127">See also</span></span>

- [<span data-ttu-id="48161-128">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="48161-128">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="48161-129">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="48161-129">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="48161-130">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="48161-130">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
