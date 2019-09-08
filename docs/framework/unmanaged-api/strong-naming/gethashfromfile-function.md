---
title: GetHashFromFile 함수
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e79c1d89d767832022d487681e0515e5e92a7f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799223"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="d2339-102">GetHashFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="d2339-102">GetHashFromFile Function</span></span>
<span data-ttu-id="d2339-103">지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="d2339-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-104">This function has been deprecated.</span></span> <span data-ttu-id="d2339-105">대신 [ICLRStrongName:: GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2339-106">구문</span><span class="sxs-lookup"><span data-stu-id="d2339-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2339-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2339-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="d2339-108">진행 해시할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d2339-109">[in, out] 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="d2339-110">유효한 알고리즘은 Win32 CryptoAPI에서 정의 되는 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="d2339-111">가 `piHashAlg` 0으로 설정 되 면 기본 알고리즘 CALG_SHA-1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d2339-112">제한이 생성 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d2339-113">진행 가 `pbHash` 가리키는 버퍼의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d2339-114">제한이 반환 `pbHash`된의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2339-115">설명</span><span class="sxs-lookup"><span data-stu-id="d2339-115">Remarks</span></span>  
 <span data-ttu-id="d2339-116">이 함수는 [GetHashFromFileW](gethashfromfilew-function.md)와 동일 합니다. 단, 파일 이름 사양은 유니코드가 아니라 ANSI입니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2339-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2339-117">Requirements</span></span>  
 <span data-ttu-id="d2339-118">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2339-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2339-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d2339-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d2339-120">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2339-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2339-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2339-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2339-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2339-122">See also</span></span>

- [<span data-ttu-id="d2339-123">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="d2339-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="d2339-124">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="d2339-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="d2339-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2339-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
