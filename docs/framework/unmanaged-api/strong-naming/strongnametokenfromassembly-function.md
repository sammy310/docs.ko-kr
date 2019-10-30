---
title: StrongNameTokenFromAssembly 함수
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
ms.openlocfilehash: 6b9eca3f2f0267870866874ea27dc65812795f41
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121125"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="8a3ae-102">StrongNameTokenFromAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="8a3ae-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="8a3ae-103">지정된 어셈블리 파일에서 강력한 이름 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="8a3ae-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-104">This function has been deprecated.</span></span> <span data-ttu-id="8a3ae-105">대신 [ICLRStrongName:: StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a3ae-106">구문</span><span class="sxs-lookup"><span data-stu-id="8a3ae-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a3ae-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a3ae-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8a3ae-108">진행 어셈블리에 대 한 PE (이식 가능한 실행) 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="8a3ae-109">제한이 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="8a3ae-110">제한이 강력한 이름 토큰의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a3ae-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="8a3ae-111">Return Value</span></span>  
 <span data-ttu-id="8a3ae-112">성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a3ae-113">주의</span><span class="sxs-lookup"><span data-stu-id="8a3ae-113">Remarks</span></span>  
 <span data-ttu-id="8a3ae-114">강력한 이름 토큰은 공개 키의 축약 된 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="8a3ae-115">토큰은 어셈블리에 서명 하는 데 사용 되는 공개 키에서 만든 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="8a3ae-116">토큰은 어셈블리에 대 한 강력한 이름의 일부 이며 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="8a3ae-117">토큰을 만든 후에는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 호출 하 여 할당 된 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-117">After the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="8a3ae-118">`StrongNameTokenFromAssembly` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3ae-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a3ae-119">Requirements</span></span>  
 <span data-ttu-id="8a3ae-120">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3ae-121">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="8a3ae-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8a3ae-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="8a3ae-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3ae-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3ae-124">참조</span><span class="sxs-lookup"><span data-stu-id="8a3ae-124">See also</span></span>

- [<span data-ttu-id="8a3ae-125">StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="8a3ae-125">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="8a3ae-126">StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="8a3ae-126">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="8a3ae-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a3ae-127">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
