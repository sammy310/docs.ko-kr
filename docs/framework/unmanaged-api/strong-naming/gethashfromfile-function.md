---
description: '자세히 알아보기: GetHashFromFile 함수'
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
ms.openlocfilehash: f91bfe8a3988b6aae563b5a852997d6fd3c309d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736598"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="9a6f7-103">GetHashFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="9a6f7-103">GetHashFromFile Function</span></span>

<span data-ttu-id="9a6f7-104">지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-104">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="9a6f7-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-105">This function has been deprecated.</span></span> <span data-ttu-id="9a6f7-106">대신 [ICLRStrongName:: GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-106">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6f7-107">구문</span><span class="sxs-lookup"><span data-stu-id="9a6f7-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a6f7-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a6f7-108">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="9a6f7-109">진행 해시할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-109">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9a6f7-110">[in, out] 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-110">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="9a6f7-111">유효한 알고리즘은 Win32 CryptoAPI에서 정의 되는 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-111">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="9a6f7-112">`piHashAlg`가 0으로 설정 되 면 기본 알고리즘 CALG_SHA-1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-112">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9a6f7-113">제한이 생성 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-113">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9a6f7-114">진행 가 가리키는 버퍼의 최대 크기입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="9a6f7-114">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9a6f7-115">제한이 반환 된의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="9a6f7-115">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a6f7-116">설명</span><span class="sxs-lookup"><span data-stu-id="9a6f7-116">Remarks</span></span>  

 <span data-ttu-id="9a6f7-117">이 함수는 [GetHashFromFileW](gethashfromfilew-function.md)와 동일 합니다. 단, 파일 이름 사양은 유니코드가 아니라 ANSI입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-117">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a6f7-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a6f7-118">Requirements</span></span>  

 <span data-ttu-id="9a6f7-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a6f7-120">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="9a6f7-120">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9a6f7-121">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a6f7-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a6f7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6f7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a6f7-123">See also</span></span>

- [<span data-ttu-id="9a6f7-124">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="9a6f7-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="9a6f7-125">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="9a6f7-125">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="9a6f7-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a6f7-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
