---
title: 어셈블리 콘텐츠
description: 이 문서에서는 어셈블리 메타데이터, 형식 메타데이터, MSIL 코드 및 리소스를 포함할 수 있는 .NET 어셈블리의 콘텐츠에 대해 설명합니다.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework]
- assemblies [.NET Core]
- single-file assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: 94df452162ed7290fab7fa267d2624e6d844a587
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378561"
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

## <a name="see-also"></a>참조

- [.NET 어셈블리](index.md)
- [어셈블리 매니페스트](manifest.md)
- [어셈블리 보안 고려 사항](security-considerations.md)
