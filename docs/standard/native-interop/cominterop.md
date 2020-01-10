---
title: .NET의 COM Interop
description: .NET에서 COM 라이브러리와 상호 운용하는 방법을 알아봅니다.
ms.date: 07/11/2019
ms.openlocfilehash: 4ea5c2330f8f90d676bfe7003a7307fc38822edf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706376"
---
# <a name="com-interop-in-net"></a><span data-ttu-id="aa976-103">.NET의 COM Interop</span><span class="sxs-lookup"><span data-stu-id="aa976-103">COM Interop in .NET</span></span>

<span data-ttu-id="aa976-104">COM(구성 요소 개체 모델)을 통해 개체는 기능을 다른 구성 요소에 노출하고 Windows 플랫폼에서 애플리케이션을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa976-104">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications on Windows platforms.</span></span> <span data-ttu-id="aa976-105">사용자가 기존 코드 베이스와 상호 운용할 수 있도록 .NET Framework에서는 COM 라이브러리와 항상 상호 운용할 수 있도록 강력한 지원 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aa976-105">To help enable users to interoperate with their existing code bases, the .NET Framework has always provided strong support for interoperating with COM libraries.</span></span> <span data-ttu-id="aa976-106">.NET Core 3.0에서 이 지원 기능의 대부분은 Windows의 .NET Core에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aa976-106">In .NET Core 3.0, a large portion of this support has been added to .NET Core on Windows.</span></span> <span data-ttu-id="aa976-107">이 설명서에서는 일반적인 COM interop 기술의 작동 방식 및 이를 활용하여 기존 COM 라이브러리와 상호 운용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa976-107">The documentation here will explain how the common COM interop techonologies work and how you can utilize them to interoperate with your existing COM libraries.</span></span>

- [<span data-ttu-id="aa976-108">COM 래퍼</span><span class="sxs-lookup"><span data-stu-id="aa976-108">COM Wrappers</span></span>](./com-wrappers.md)
- [<span data-ttu-id="aa976-109">COM 호출 가능 래퍼</span><span class="sxs-lookup"><span data-stu-id="aa976-109">COM Callable Wrappers</span></span>](./com-callable-wrapper.md)
- [<span data-ttu-id="aa976-110">런타임 호출 가능 래퍼</span><span class="sxs-lookup"><span data-stu-id="aa976-110">Runtime Callable Wrappers</span></span>](./runtime-callable-wrapper.md)
- [<span data-ttu-id="aa976-111">COM 상호 운용성을 위한 .NET 형식 정규화</span><span class="sxs-lookup"><span data-stu-id="aa976-111">Qualifying .NET Types for COM Interoperation</span></span>](./qualify-net-types-for-interoperation.md)
