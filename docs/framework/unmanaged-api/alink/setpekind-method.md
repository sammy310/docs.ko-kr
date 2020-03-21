---
title: SetPEKind 메서드
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179385"
---
# <a name="setpekind-method"></a><span data-ttu-id="6a11a-102">SetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="6a11a-102">SetPEKind Method</span></span>
<span data-ttu-id="6a11a-103">컴퓨터별 또는 기계에 구애받지 않는 휴대용 실행 유형이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a11a-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a11a-104">구문</span><span class="sxs-lookup"><span data-stu-id="6a11a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="6a11a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a11a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6a11a-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6a11a-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="6a11a-107">PE 형식을 설정할 파일의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6a11a-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="6a11a-108">언바운드 넷 `AssemblyID` 모듈을 나타내지 않으면 NULL이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a11a-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="6a11a-109">[CorPEKind 열거형에](../metadata/corpekind-enumeration.md)표시된 PE 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6a11a-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="6a11a-110">NT 헤더에 표시된 대로 대상 컴퓨터 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="6a11a-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a11a-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="6a11a-111">Return Value</span></span>  
 <span data-ttu-id="6a11a-112">메서드가 성공하면 S_OK 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11a-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a11a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a11a-113">Requirements</span></span>  
 <span data-ttu-id="6a11a-114">alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a11a-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a11a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a11a-115">See also</span></span>

- [<span data-ttu-id="6a11a-116">GetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="6a11a-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="6a11a-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a11a-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6a11a-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a11a-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6a11a-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="6a11a-119">ALink API</span></span>](index.md)
