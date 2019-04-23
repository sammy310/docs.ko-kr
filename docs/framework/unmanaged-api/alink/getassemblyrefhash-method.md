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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fa8d42f9e849db6a02f6c62b37e04cf5dee016e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119654"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="21975-102">GetAssemblyRefHash 메서드</span><span class="sxs-lookup"><span data-stu-id="21975-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="21975-103">지정된 된 어셈블리에 대 한 해시 blob를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="21975-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21975-104">구문</span><span class="sxs-lookup"><span data-stu-id="21975-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="21975-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="21975-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="21975-106">해시는 참조 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="21975-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="21975-107">생성 되는 해시 blob을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="21975-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="21975-108">해시 blob의 바이트에서 크기를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="21975-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21975-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="21975-109">Return Value</span></span>  
 <span data-ttu-id="21975-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="21975-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21975-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21975-111">Requirements</span></span>  
 <span data-ttu-id="21975-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="21975-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21975-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="21975-113">See also</span></span>

- [<span data-ttu-id="21975-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21975-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="21975-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21975-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="21975-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="21975-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
