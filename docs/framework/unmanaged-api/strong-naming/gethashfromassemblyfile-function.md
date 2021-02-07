---
description: '자세히 알아보기: GetHashFromAssemblyFile 함수'
title: GetHashFromAssemblyFile 함수
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
ms.openlocfilehash: 79cc6289ebcf33f5a9ea8b4ef139c4b2a67e55e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736780"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="d1e4c-103">GetHashFromAssemblyFile 함수</span><span class="sxs-lookup"><span data-stu-id="d1e4c-103">GetHashFromAssemblyFile Function</span></span>

<span data-ttu-id="d1e4c-104">지정된 해시 알고리즘을 사용하여 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-104">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="d1e4c-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-105">This function has been deprecated.</span></span> <span data-ttu-id="d1e4c-106">대신 [ICLRStrongName:: GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-106">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e4c-107">구문</span><span class="sxs-lookup"><span data-stu-id="d1e4c-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1e4c-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1e4c-108">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="d1e4c-109">진행 해시할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-109">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d1e4c-110">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d1e4c-111">기본 해시 알고리즘에 대해 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-111">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d1e4c-112">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d1e4c-113">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d1e4c-114">제한이 반환 된 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="d1e4c-114">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1e4c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1e4c-115">Requirements</span></span>  

 <span data-ttu-id="d1e4c-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e4c-117">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="d1e4c-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d1e4c-118">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e4c-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1e4c-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e4c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e4c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1e4c-120">See also</span></span>

- [<span data-ttu-id="d1e4c-121">GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="d1e4c-121">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="d1e4c-122">GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="d1e4c-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="d1e4c-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1e4c-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
