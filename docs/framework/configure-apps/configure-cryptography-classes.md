---
title: 암호화 클래스 구성
description: 컴퓨터 관리자가 .NET 및 응용 프로그램에서 사용 하는 기본 암호화 알고리즘과 알고리즘 구현을 어떻게 구성할 수 있는지 이해 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 5d12aae31ec78f80bea7df1bb0f37ac78dc37de2
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105061"
---
# <a name="configuring-cryptography-classes"></a>암호화 클래스 구성
Windows SDK를 사용 하 여 컴퓨터 관리자는 .NET Framework 및 적절 하 게 작성 된 응용 프로그램에서 사용 하는 기본 암호화 알고리즘과 알고리즘 구현을 구성할 수 있습니다.  예를 들어, 암호화 알고리즘의 자체 구현을 포함 하는 엔터프라이즈는 Windows SDK에서 제공 하는 구현 대신 기본값을 구현 하도록 할 수 있습니다. 암호화를 사용 하는 관리 되는 응용 프로그램은 항상 특정 구현에 명시적으로 바인딩하도록 선택할 수 있지만 암호화 구성 시스템을 사용 하 여 암호화 개체를 만드는 것이 좋습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [알고리즘 이름을 암호화 클래스에 매핑](map-algorithm-names-to-cryptography-classes.md)  
 암호화 클래스에 알고리즘 이름을 매핑하는 방법을 설명 합니다.  
  
 [개체 식별자를 암호화 알고리즘에 매핑](map-object-identifiers-to-cryptography-algorithms.md)  
 암호화 알고리즘에 개체 식별자를 매핑하는 방법에 대해 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [암호화 서비스](../../standard/security/cryptographic-services.md)  
 Windows SDK에서 제공 하는 암호화 서비스에 대 한 개요를 제공 합니다.  
  
 [암호화 설정 스키마](./file-schema/cryptography/index.md)  
 암호화 알고리즘을 구현하는 클래스에 편리한 알고리즘 이름을 매핑하는 요소에 대해 설명합니다.
