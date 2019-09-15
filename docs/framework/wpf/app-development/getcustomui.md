---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: a9c4c9d597f5cc1b172213d49a3dd5b8f1c1f671
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991371"
---
# <a name="getcustomui"></a>GetCustomUI
구현 된 경우 호스트에서 사용자 지정 진행률 및 오류 메시지를 가져오기 위해 Presentationhost.exe에 의해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwzProgressAssemblyName`  
  
 제한이 호스트에서 제공 하는 진행률 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.  
  
 `pwzProgressClassName`  
  
 제한이 호스트에서 제공 하는 진행률 사용자 인터페이스인 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 클래스의 이름입니다 .를 사용 <xref:System.Windows.Controls.Page> 하는 파일이 최상위 요소입니다. 이 클래스는에 지정 `pwzProgressAssemblyName`된 어셈블리에 상주 합니다.  
  
 `pwzErrorAssemblyName`  
  
 제한이 호스트에서 제공한 오류 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.  
  
 `pwzErrorClassName`  
  
 제한이 호스트에서 제공 하는 오류 사용자 인터페이스인 클래스의 이름입니다 .를 사용 <xref:System.Windows.Controls.Page> 하는 XAML 파일은 최상위 요소입니다. 이 클래스는에 지정 `pwzErrorAssemblyName`된 어셈블리에 상주 합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 HRESULT: 무시됩니다.  
  
## <a name="remarks"></a>설명  
 호스트 응용 프로그램에 Presentationhost.exe의 기본 사용자 인터페이스가 준수 하지 않을 수 있는 특정 테마가 있을 수 있습니다. 이 경우 호스트 응용 프로그램은 [GetCustomUI](getcustomui.md) 를 구현 하 여 진행률 및 오류 사용자 인터페이스를 presentationhost.exe로 반환할 수 있습니다. Presentationhost.exe는 기본 사용자 인터페이스를 사용 하기 전에 항상 [GetCustomUI](getcustomui.md) 를 호출 합니다.  
  
 이 함수는 Presentationhost.exe의 초기화 중에 한 번 호출 됩니다.  
  
## <a name="see-also"></a>참고자료

- [IWpfHostSupport](iwpfhostsupport.md)
