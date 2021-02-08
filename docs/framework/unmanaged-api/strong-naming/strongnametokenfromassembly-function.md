---
description: '자세히 알아보기: StrongNameTokenFromAssembly 함수'
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
ms.openlocfilehash: 3646d441da4885624c15d5e53670a8dd8db45160
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794483"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="fcc9b-103">StrongNameTokenFromAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="fcc9b-103">StrongNameTokenFromAssembly Function</span></span>

<span data-ttu-id="fcc9b-104">지정된 어셈블리 파일에서 강력한 이름 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-104">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="fcc9b-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-105">This function has been deprecated.</span></span> <span data-ttu-id="fcc9b-106">대신 [ICLRStrongName:: StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-106">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc9b-107">구문</span><span class="sxs-lookup"><span data-stu-id="fcc9b-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcc9b-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fcc9b-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="fcc9b-109">진행 어셈블리에 대 한 PE (이식 가능한 실행) 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-109">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="fcc9b-110">제한이 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-110">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="fcc9b-111">제한이 강력한 이름 토큰의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-111">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcc9b-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="fcc9b-112">Return Value</span></span>  

 <span data-ttu-id="fcc9b-113">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcc9b-114">설명</span><span class="sxs-lookup"><span data-stu-id="fcc9b-114">Remarks</span></span>  

 <span data-ttu-id="fcc9b-115">강력한 이름 토큰은 공개 키의 축약 된 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-115">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="fcc9b-116">토큰은 어셈블리에 서명 하는 데 사용 되는 공개 키에서 만든 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-116">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="fcc9b-117">토큰은 어셈블리에 대 한 강력한 이름의 일부 이며 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-117">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="fcc9b-118">토큰을 만든 후에는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 호출 하 여 할당 된 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-118">After the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="fcc9b-119">`StrongNameTokenFromAssembly`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-119">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcc9b-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fcc9b-120">Requirements</span></span>  

 <span data-ttu-id="fcc9b-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcc9b-122">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="fcc9b-122">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fcc9b-123">**라이브러리:** mscoree.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcc9b-123">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="fcc9b-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc9b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc9b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcc9b-125">See also</span></span>

- [<span data-ttu-id="fcc9b-126">StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="fcc9b-126">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="fcc9b-127">StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="fcc9b-127">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="fcc9b-128">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fcc9b-128">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
