---
description: '자세한 정보: GetPublicKeyToken 메서드'
title: GetPublicKeyToken 메서드
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
ms.openlocfilehash: b864c1dc61c7498ccca6aa04ef29b57a30e1a9ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718423"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="7ae61-103">GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="7ae61-103">GetPublicKeyToken Method</span></span>

<span data-ttu-id="7ae61-104">지정 된 keyfile 또는 키 컨테이너에 대 한 공개 키 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ae61-104">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae61-105">구문</span><span class="sxs-lookup"><span data-stu-id="7ae61-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ae61-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ae61-106">Parameters</span></span>  

 `pszKeyFile`  
 <span data-ttu-id="7ae61-107">키의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7ae61-107">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="7ae61-108">키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7ae61-108">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="7ae61-109">키 토큰을 저장할 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7ae61-109">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="7ae61-110">로 표시 되는 버퍼의 크기 (바이트)를 지정 합니다 `pvPublicKeyToken` .</span><span class="sxs-lookup"><span data-stu-id="7ae61-110">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="7ae61-111">반환 시 실제 사용 된 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ae61-111">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ae61-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="7ae61-112">Return Value</span></span>  

 <span data-ttu-id="7ae61-113">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ae61-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae61-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ae61-114">Requirements</span></span>  

 <span data-ttu-id="7ae61-115">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ae61-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae61-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ae61-116">See also</span></span>

- [<span data-ttu-id="7ae61-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ae61-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7ae61-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ae61-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7ae61-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="7ae61-119">ALink API</span></span>](index.md)
