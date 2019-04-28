---
title: StrongNameTokenFromAssemblyEx 함수
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95f00fea637b5263699779b7abe9863d266d7f19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786193"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="8e420-102">StrongNameTokenFromAssemblyEx 함수</span><span class="sxs-lookup"><span data-stu-id="8e420-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="8e420-103">지정 된 어셈블리 파일에서 강력한 이름 토큰을 만들고 공개 키 토큰이 나타내는 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="8e420-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-104">This function has been deprecated.</span></span> <span data-ttu-id="8e420-105">사용 된 [iclrstrongname:: Strongnametokenfromassemblyex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e420-106">구문</span><span class="sxs-lookup"><span data-stu-id="8e420-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e420-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e420-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8e420-108">[in] 어셈블리의 pe (이식 가능) 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="8e420-109">[out] 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="8e420-110">[out] 강력한 이름 토큰의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="8e420-111">[out] 반환 된 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="8e420-112">[out] 공개 키의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e420-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="8e420-113">Return Value</span></span>  
 <span data-ttu-id="8e420-114">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e420-115">설명</span><span class="sxs-lookup"><span data-stu-id="8e420-115">Remarks</span></span>  
 <span data-ttu-id="8e420-116">강력한 이름 토큰은 공개 키의 축약 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="8e420-117">토큰은 어셈블리 서명에 사용 된 공개 키에서 생성 되는 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="8e420-118">토큰에는 어셈블리에 대 한 강력한 이름의 일부인 되며 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="8e420-119">키가 검색 후 토큰이 만들어지기 호출 해야 합니다 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 할당 된 메모리를 해제 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="8e420-120">경우는 `StrongNameTokenFromAssemblyEx` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8e420-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e420-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e420-121">Requirements</span></span>  
 <span data-ttu-id="8e420-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e420-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e420-123">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8e420-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8e420-124">**라이브러리:** Mscoree.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8e420-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="8e420-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e420-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e420-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="8e420-126">See also</span></span>

- [<span data-ttu-id="8e420-127">StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="8e420-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="8e420-128">StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="8e420-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="8e420-129">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e420-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
