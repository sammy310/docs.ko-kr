---
title: StrongNameSignatureSize 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f98b971e430a2c35a4c484f4f9c4bf387c640c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798960"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="161e1-102">StrongNameSignatureSize 함수</span><span class="sxs-lookup"><span data-stu-id="161e1-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="161e1-103">강력한 이름 서명의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="161e1-104">`StrongNameSignatureSize`는 일반적으로 컴파일러가 지연 서명 된 어셈블리를 만들 때 파일에서 예약할 공간의 크기를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="161e1-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-105">This function has been deprecated.</span></span> <span data-ttu-id="161e1-106">대신 [ICLRStrongName:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="161e1-107">구문</span><span class="sxs-lookup"><span data-stu-id="161e1-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="161e1-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="161e1-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="161e1-109">진행 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 [PublicKeyBlob](publickeyblob-structure.md) 형식의 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="161e1-110">진행 의 `pbPublicKeyBlob`크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="161e1-111">진행 강력한 이름 서명을 저장 하는 데 필요한 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="161e1-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="161e1-112">Return Value</span></span>  
 <span data-ttu-id="161e1-113">`true`성공적으로 완료 되 면 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="161e1-114">설명</span><span class="sxs-lookup"><span data-stu-id="161e1-114">Remarks</span></span>  
 <span data-ttu-id="161e1-115">`StrongNameSignatureSize` 함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="161e1-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="161e1-116">Requirements</span></span>  
 <span data-ttu-id="161e1-117">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="161e1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="161e1-118">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="161e1-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="161e1-119">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="161e1-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="161e1-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="161e1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="161e1-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="161e1-121">See also</span></span>

- [<span data-ttu-id="161e1-122">StrongNameSignatureSize 메서드</span><span class="sxs-lookup"><span data-stu-id="161e1-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="161e1-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="161e1-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
