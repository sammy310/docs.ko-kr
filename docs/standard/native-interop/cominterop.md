---
title: .NET의 COM Interop
description: .NET에서 COM 라이브러리와 상호 운용하는 방법을 알아봅니다.
ms.date: 07/11/2019
ms.openlocfilehash: 63205ae5c09d6c3929da13788eb781cd975ca814
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627376"
---
# <a name="com-interop-in-net"></a>.NET의 COM Interop

COM(구성 요소 개체 모델)을 통해 개체는 기능을 다른 구성 요소에 노출하고 Windows 플랫폼에서 애플리케이션을 호스트할 수 있습니다. 사용자가 기존 코드 베이스와 상호 운용할 수 있도록 .NET Framework에서는 COM 라이브러리와 항상 상호 운용할 수 있도록 강력한 지원 기능을 제공합니다. .NET Core 3.0에서 이 지원 기능의 대부분은 Windows의 .NET Core에 추가되었습니다. 여기의 설명서에서는 일반적인 COM interop 기술의 작동 방식과 기존 COM 라이브러리와의 상호 작용을 활용 하는 방법을 설명 합니다.

- [COM 래퍼](./com-wrappers.md)
- [COM 호출 가능 래퍼](./com-callable-wrapper.md)
- [런타임 호출 가능 래퍼](./runtime-callable-wrapper.md)
- [COM 상호 운용성을 위한 .NET 형식 정규화](./qualify-net-types-for-interoperation.md)
