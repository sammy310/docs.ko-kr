---
title: PublicKeyBlob 구조체
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
ms.openlocfilehash: 6c58a0726e0869178838999c6b000e0ad975f145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140612"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="6d7a2-102">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="6d7a2-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="6d7a2-103">공개/개인 키 쌍의 공개 키를 이진 형식으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d7a2-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d7a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d7a2-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="6d7a2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6d7a2-105">Members</span></span>  
  
|<span data-ttu-id="6d7a2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6d7a2-106">Member</span></span>|<span data-ttu-id="6d7a2-107">설명</span><span class="sxs-lookup"><span data-stu-id="6d7a2-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="6d7a2-108">공개 키의 Wincrypt.h에 정의 된 형식 `ALG_ID`의 서명 알고리즘에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6d7a2-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="6d7a2-109">공개 키의 Wincrypt.h에 정의 된 대로 형식 `ALG_ID`의 해시 알고리즘에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6d7a2-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="6d7a2-110">키의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="6d7a2-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="6d7a2-111">CryptoAPI에서 반환 된 형식의 키 값을 포함 하는 가변 길이 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6d7a2-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d7a2-112">주의</span><span class="sxs-lookup"><span data-stu-id="6d7a2-112">Remarks</span></span>  
 <span data-ttu-id="6d7a2-113">`PublicKeyBlob` 구조체는 [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)및 기타 강력한 이름 함수에서 공개/개인 키 쌍의 공개 키를 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d7a2-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d7a2-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d7a2-114">Requirements</span></span>  
 <span data-ttu-id="6d7a2-115">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d7a2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d7a2-116">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="6d7a2-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6d7a2-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d7a2-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d7a2-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d7a2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d7a2-119">참조</span><span class="sxs-lookup"><span data-stu-id="6d7a2-119">See also</span></span>

- [<span data-ttu-id="6d7a2-120">StrongNameGetPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="6d7a2-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="6d7a2-121">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="6d7a2-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
