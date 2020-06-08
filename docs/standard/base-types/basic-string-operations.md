---
title: .NET의 기본적인 문자열 작업
description: 문자열에서 수행할 수 있는 기본 작업에 대해 알아봅니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
ms.custom: seadec18
ms.openlocfilehash: 8c19f6bcbdf5e4829c91aee1e2fd631537ed2e0a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277754"
---
# <a name="basic-string-operations-in-net"></a>.NET의 기본적인 문자열 작업

애플리케이션에서 사용자 입력을 기반으로 메시지를 생성하여 사용자에게 응답하는 경우가 많습니다. 예를 들어 웹 사이트에서 사용자 이름을 포함하는 특수 인사말을 사용하여 새로 로그온한 사용자에게 응답하는 경우도 드물지 않습니다.

<xref:System.String?displayProperty=nameWithType> 및 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스의 여러 메서드를 통해 사용자 인터페이스에 표시할 사용자 지정 문자열을 동적으로 생성할 수 있습니다. 이러한 메서드는 바이트 배열에서 새 문자열 만들기, 문자열 값 비교, 기존 문자열 수정 등의 여러 기본적인 문자열 작업을 수행하는 데에도 도움이 됩니다.

## <a name="related-sections"></a>관련 단원

[.NET에서 형식 변환](type-conversion.md)\
형식 간에 변환하는 방법을 설명합니다.  

[형식 서식 지정](formatting-types.md)\
형식 지정자를 사용하여 문자열 서식을 지정하는 방법을 설명합니다.
