---
title: Tlbexp 도우미 함수(관리되지 않는 API 참조)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: 9386918f3574720d90bda7e8da592fa0c91160e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708246"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="5cc26-102">Tlbexp 도우미 함수(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="5cc26-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>

<span data-ttu-id="5cc26-103">[형식 라이브러리 내보내기 도구](../../tools/tlbexp-exe-type-library-exporter.md)(Tlbexp.exe)는 TlbRef.dll이라는 동적 링크 라이브러리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc26-103">The [Type Library Exporter tool](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="5cc26-104">이 DLL에는 어셈블리-형식 라이브러리 전환 프로세스 중 내보내기 도구에서 사용하는 인터페이스 하나와 도우미 함수 두 개가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc26-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5cc26-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5cc26-105">In This Section</span></span>  

 [<span data-ttu-id="5cc26-106">GetTypeLibInfo 함수</span><span class="sxs-lookup"><span data-stu-id="5cc26-106">GetTypeLibInfo Function</span></span>](gettypelibinfo-function.md)  
 <span data-ttu-id="5cc26-107">형식 라이브러리에 대한 지역화 및 운영 체제 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc26-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="5cc26-108">LoadTypeLibWithResolver 함수</span><span class="sxs-lookup"><span data-stu-id="5cc26-108">LoadTypeLibWithResolver Function</span></span>](loadtypelibwithresolver-function.md)  
 <span data-ttu-id="5cc26-109">[ITypeLibResolver 인터페이스](itypelibresolver-interface.md) 구현을 통해 형식 라이브러리를 로드하고 참조된 형식 라이브러리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc26-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="5cc26-110">ITypeLibResolver 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cc26-110">ITypeLibResolver Interface</span></span>](itypelibresolver-interface.md)  
 <span data-ttu-id="5cc26-111">형식 라이브러리의 정규화된 경로를 반환하는 [ResolveTypeLib 메서드](resolvetypelib-method.md)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc26-111">Provides the [ResolveTypeLib method](resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
