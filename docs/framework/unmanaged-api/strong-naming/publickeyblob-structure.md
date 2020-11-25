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
ms.openlocfilehash: 42cd3cc22fbbb8eb3d5ac44544fce36650b6461f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705932"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="11757-102">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="11757-102">PublicKeyBlob Structure</span></span>

<span data-ttu-id="11757-103">공개/개인 키 쌍의 공개 키를 이진 형식으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11757-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11757-104">구문</span><span class="sxs-lookup"><span data-stu-id="11757-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="11757-105">멤버</span><span class="sxs-lookup"><span data-stu-id="11757-105">Members</span></span>  
  
|<span data-ttu-id="11757-106">멤버</span><span class="sxs-lookup"><span data-stu-id="11757-106">Member</span></span>|<span data-ttu-id="11757-107">설명</span><span class="sxs-lookup"><span data-stu-id="11757-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="11757-108">`ALG_ID`공개 키의 서명 알고리즘 (wincrypt.h에 정의 된 형식)에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="11757-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="11757-109">`ALG_ID`공개 키의 해시 알고리즘 (wincrypt.h에 정의 된 형식)에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="11757-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="11757-110">키의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="11757-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="11757-111">CryptoAPI에서 반환 된 형식의 키 값을 포함 하는 가변 길이 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="11757-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11757-112">설명</span><span class="sxs-lookup"><span data-stu-id="11757-112">Remarks</span></span>  

 <span data-ttu-id="11757-113">`PublicKeyBlob`구조체는 [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)및 기타 강력한 이름 함수에서 공개/개인 키 쌍의 공개 키를 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11757-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11757-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11757-114">Requirements</span></span>  

 <span data-ttu-id="11757-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11757-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11757-116">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="11757-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="11757-117">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11757-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11757-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11757-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11757-119">참조</span><span class="sxs-lookup"><span data-stu-id="11757-119">See also</span></span>

- [<span data-ttu-id="11757-120">StrongNameGetPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="11757-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="11757-121">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="11757-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
