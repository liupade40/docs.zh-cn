---
title: "ICorProfilerInfo4::GetCodeInfo3 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetCodeInfo3
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 87a93220bbaf3930f8ac2671efc0f19b2df8aee5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a>ICorProfilerInfo4::GetCodeInfo3 方法
获取本机代码的范围，该代码与指定函数的 JIT 重新编译版本相关联。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a>参数  
 `functionID`  
 [in] 与本机代码关联的函数的 ID。  
  
 `reJitId`  
 [in] JIT 重新编译的函数的标识。  
  
 `cCodeInfos`  
 [in] `codeInfos` 数组的大小。  
  
 `pcCodeInfos`  
 [out]指向的总数的指针[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构可用。  
  
 `codeInfos`  
 [out] 调用方提供的缓冲区。 返回此方法后，它包含一个 `COR_PRF_CODE_INFO` 结构数组，每个结构描述一个本机代码块。  
  
## <a name="remarks"></a>备注  
 `GetCodeInfo3`方法类似于是[GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)，只不过它将获取包含指定的 IP 地址的函数的 JIT 重新编译 ID。  
  
> [!NOTE]
>  `GetCodeInfo3`可以触发垃圾回收，而[GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)将不会。 有关详细信息，请参阅[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT。  
  
 范围按公共中间语言 (CIL) 偏移递增的顺序进行排序。  
  
 后`GetCodeInfo3`返回时，您必须验证`codeInfos`缓冲区是否足够大以包含所有[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构。 为此，请将 `cCodeInfos` 的值和 `cchName` 参数的值进行比较。 如果`cCodeInfos`除以的大小[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构小于`pcCodeInfos`，分配更大`codeInfos`缓冲区，更新`cCodeInfos`与新的更大大小，并调用`GetCodeInfo3`试。  
  
 或者，可先用长度为零的 `codeInfos` 缓冲区调用 `GetCodeInfo3` 以获取正确的缓冲区大小。 然后，可以设置`codeInfos`缓冲区中返回的值的大小`pcCodeInfos`，再乘以的大小[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构，并调用`GetCodeInfo3`试。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [GetCodeInfo2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
 [ICorProfilerInfo4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [分析接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)