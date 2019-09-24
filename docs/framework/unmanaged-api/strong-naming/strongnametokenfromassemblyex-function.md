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
ms.openlocfilehash: c000aad12000a9c76fb6dd805a9b002c021be6ef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798835"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="0534e-102">StrongNameTokenFromAssemblyEx 함수</span><span class="sxs-lookup"><span data-stu-id="0534e-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="0534e-103">지정 된 어셈블리 파일에서 강력한 이름 토큰을 만들고 토큰이 나타내는 공개 키를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="0534e-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-104">This function has been deprecated.</span></span> <span data-ttu-id="0534e-105">대신 [ICLRStrongName:: StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0534e-106">구문</span><span class="sxs-lookup"><span data-stu-id="0534e-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0534e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0534e-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0534e-108">진행 어셈블리에 대 한 PE (이식 가능한 실행) 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="0534e-109">제한이 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="0534e-110">제한이 강력한 이름 토큰의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="0534e-111">제한이 반환 된 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="0534e-112">제한이 공개 키의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0534e-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="0534e-113">Return Value</span></span>  
 <span data-ttu-id="0534e-114">`true`성공적으로 완료 되 면 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0534e-115">설명</span><span class="sxs-lookup"><span data-stu-id="0534e-115">Remarks</span></span>  
 <span data-ttu-id="0534e-116">강력한 이름 토큰은 공개 키의 축약 된 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="0534e-117">토큰은 어셈블리에 서명 하는 데 사용 되는 공개 키에서 만든 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="0534e-118">토큰은 어셈블리에 대 한 강력한 이름의 일부 이며 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="0534e-119">키를 검색 하 고 토큰을 만든 후에는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 호출 하 여 할당 된 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="0534e-120">`StrongNameTokenFromAssemblyEx`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0534e-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0534e-121">Requirements</span></span>  
 <span data-ttu-id="0534e-122">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0534e-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0534e-123">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="0534e-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0534e-124">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0534e-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="0534e-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0534e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0534e-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="0534e-126">See also</span></span>

- [<span data-ttu-id="0534e-127">StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="0534e-127">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="0534e-128">StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="0534e-128">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="0534e-129">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0534e-129">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
