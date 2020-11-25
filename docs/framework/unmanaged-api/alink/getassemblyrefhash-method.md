---
title: GetAssemblyRefHash 메서드
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
ms.openlocfilehash: af040c4a6c9b85930d2d9261f8587ba69eb204e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721480"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="669a2-102">GetAssemblyRefHash 메서드</span><span class="sxs-lookup"><span data-stu-id="669a2-102">GetAssemblyRefHash Method</span></span>

<span data-ttu-id="669a2-103">지정 된 어셈블리에 대 한 해시 blob를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="669a2-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="669a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="669a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="669a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="669a2-105">Parameters</span></span>  

 `FileToken`  
 <span data-ttu-id="669a2-106">해시가 참조할 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="669a2-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="669a2-107">결과 해시 blob을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="669a2-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="669a2-108">해시 blob의 크기 (바이트)를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="669a2-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="669a2-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="669a2-109">Return Value</span></span>  

 <span data-ttu-id="669a2-110">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="669a2-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="669a2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="669a2-111">Requirements</span></span>  

 <span data-ttu-id="669a2-112">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="669a2-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="669a2-113">참조</span><span class="sxs-lookup"><span data-stu-id="669a2-113">See also</span></span>

- [<span data-ttu-id="669a2-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="669a2-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="669a2-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="669a2-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="669a2-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="669a2-116">ALink API</span></span>](index.md)
