---
title: SetAssemblyFile2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aba11ccd61b65d2a779b39db8e0e082cf4d4015b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787223"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="377dd-102">SetAssemblyFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="377dd-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="377dd-103">새 어셈블리에 대 한 및 옵션의 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="377dd-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="377dd-104">바인딩되지 않은 모듈을 생성할 때이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="377dd-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377dd-105">구문</span><span class="sxs-lookup"><span data-stu-id="377dd-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="377dd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="377dd-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="377dd-107">매니페스트 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="377dd-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="377dd-108">이 파일에 대 한 [IMetaDataEmit2 interface](../metadata/imetadataemit2-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="377dd-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="377dd-109">[Assemblyflags 열거형](../metadata/assemblyflags-enumeration.md)으로 표시 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="377dd-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="377dd-110">생성 되는 어셈블리에 대 한 고유 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="377dd-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="377dd-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="377dd-111">Return Value</span></span>  
 <span data-ttu-id="377dd-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="377dd-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377dd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="377dd-113">Requirements</span></span>  
 <span data-ttu-id="377dd-114">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="377dd-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377dd-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="377dd-115">See also</span></span>

- [<span data-ttu-id="377dd-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="377dd-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="377dd-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="377dd-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="377dd-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="377dd-118">ALink API</span></span>](index.md)
