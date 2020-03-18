---
title: 어셈블리 콘텐츠
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework]
- assemblies [.NET Core]
- single-file assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: bee9d5422ec3101b2486f233ae0816ae3643f4e7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75345568"
---
# <a name="assembly-contents"></a>어셈블리 콘텐츠

일반적으로 정적 어셈블리는 네 가지 요소로 구성됩니다.

- 어셈블리 메타데이터를 포함하는 [어셈블리 매니페스트](manifest.md)

- 형식 메타데이터  

- 형식을 구현하는 MSIL(Microsoft Intermediate Language) 코드 하나 이상의 소스 코드 파일에서 컴파일러에 의해 생성됩니다.

- [리소스](../../framework/resources/index.md) 집합.  

어셈블리 매니페스트만 있으면 되지만, 어셈블리에 의미 있는 기능을 부여하려면 형식 또는 리소스가 필요합니다.

다음 그림은 단일 물리적 파일에 그룹화된 이러한 요소를 보여 줍니다.

![MyAssembly.dll이라는 단일 파일 어셈블리](./media/contents/single-file-assembly.gif)

소스 코드를 디자인하는 경우 애플리케이션의 기능을 하나 이상의 파일로 분리하는 방법에 대해 명시적으로 결정해야 합니다. 또한 .NET 코드를 디자인하는 경우에도 해당 기능을 하나 이상의 어셈블리로 분리하는 방법에 대해 결정해야 합니다.

## <a name="see-also"></a>참고 항목

- [.NET 어셈블리](index.md)
- [어셈블리 매니페스트](manifest.md)
- [어셈블리 보안 고려 사항](security-considerations.md)
