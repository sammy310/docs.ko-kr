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
ms.openlocfilehash: dfbc10bdbe633450dee2e27524c29ead21fb739e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445538"
---
# <a name="setpekind-method"></a><span data-ttu-id="78d7a-102">SetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="78d7a-102">SetPEKind Method</span></span>
<span data-ttu-id="78d7a-103">이식 가능한 실행 파일 유형 (컴퓨터 특정 컴퓨터 또는 컴퓨터 관계 없음)을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78d7a-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78d7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="78d7a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="78d7a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78d7a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="78d7a-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="78d7a-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="78d7a-107">PE 형식을 설정할 파일의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="78d7a-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="78d7a-108">`AssemblyID`에서 바인딩되지 않은 .netmodule을 나타내지 않는 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78d7a-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="78d7a-109">[CorPEKind 열거](../metadata/corpekind-enumeration.md)에 표시 되는 PE의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="78d7a-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="78d7a-110">NT 헤더에 표시 된 대상 컴퓨터 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="78d7a-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78d7a-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="78d7a-111">Return Value</span></span>  
 <span data-ttu-id="78d7a-112">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="78d7a-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78d7a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78d7a-113">Requirements</span></span>  
 <span data-ttu-id="78d7a-114">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="78d7a-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d7a-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="78d7a-115">See also</span></span>

- [<span data-ttu-id="78d7a-116">GetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="78d7a-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="78d7a-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78d7a-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="78d7a-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78d7a-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="78d7a-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="78d7a-119">ALink API</span></span>](index.md)
