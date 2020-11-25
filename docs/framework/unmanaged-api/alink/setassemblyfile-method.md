---
title: SetAssemblyFile 메서드
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 45eed17b91f70d4188d1d89fc91a41455f3e845b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732647"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="1aadf-102">SetAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="1aadf-102">SetAssemblyFile Method</span></span>

<span data-ttu-id="1aadf-103">빌드할 어셈블리의 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aadf-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="1aadf-104">바인딩되지 않은 모듈을 생성할 때 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1aadf-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aadf-105">구문</span><span class="sxs-lookup"><span data-stu-id="1aadf-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aadf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1aadf-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="1aadf-107">매니페스트 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1aadf-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="1aadf-108">[IMetaDataEmit interface](../metadata/imetadataemit-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1aadf-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="1aadf-109">[Assemblyflags 열거형](../metadata/assemblyflags-enumeration.md)에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="1aadf-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="1aadf-110">결과 어셈블리의 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1aadf-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1aadf-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="1aadf-111">Return Value</span></span>  

 <span data-ttu-id="1aadf-112">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aadf-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aadf-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1aadf-113">Requirements</span></span>  

 <span data-ttu-id="1aadf-114">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aadf-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aadf-115">참조</span><span class="sxs-lookup"><span data-stu-id="1aadf-115">See also</span></span>

- [<span data-ttu-id="1aadf-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1aadf-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1aadf-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1aadf-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1aadf-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="1aadf-118">ALink API</span></span>](index.md)
