add_circt_dialect(RTG rtg)
add_circt_doc(RTG Dialects/RTGOps -gen-op-doc)
add_circt_doc(RTG Dialects/RTGTypes -gen-typedef-doc -dialect rtg)

set(LLVM_TARGET_DEFINITIONS RTG.td)
mlir_tablegen(RTGEnums.h.inc -gen-enum-decls)
mlir_tablegen(RTGEnums.cpp.inc -gen-enum-defs)
add_public_tablegen_target(CIRCTRTGEnumsIncGen)

set(LLVM_TARGET_DEFINITIONS RTGInterfaces.td)
mlir_tablegen(RTGOpInterfaces.h.inc -gen-op-interface-decls)
mlir_tablegen(RTGOpInterfaces.cpp.inc -gen-op-interface-defs)
add_public_tablegen_target(CIRCTRTGOpInterfacesIncGen)
add_dependencies(circt-headers CIRCTRTGOpInterfacesIncGen)

mlir_tablegen(RTGTypeInterfaces.h.inc -gen-type-interface-decls)
mlir_tablegen(RTGTypeInterfaces.cpp.inc -gen-type-interface-defs)
add_public_tablegen_target(CIRCTRTGTypeInterfacesIncGen)
add_dependencies(circt-headers CIRCTRTGTypeInterfacesIncGen)

mlir_tablegen(RTGAttrInterfaces.h.inc -gen-attr-interface-decls)
mlir_tablegen(RTGAttrInterfaces.cpp.inc -gen-attr-interface-defs)
add_public_tablegen_target(CIRCTRTGAttrInterfacesIncGen)
add_dependencies(circt-headers CIRCTRTGAttrInterfacesIncGen)

set(LLVM_TARGET_DEFINITIONS RTGISAAssemblyInterfaces.td)
mlir_tablegen(RTGISAAssemblyAttrInterfaces.h.inc -gen-attr-interface-decls)
mlir_tablegen(RTGISAAssemblyAttrInterfaces.cpp.inc -gen-attr-interface-defs)
add_public_tablegen_target(CIRCTRTGISAAssemblyAttrInterfacesIncGen)
add_dependencies(circt-headers CIRCTRTGISAAssemblyAttrInterfacesIncGen)

mlir_tablegen(RTGISAAssemblyTypeInterfaces.h.inc -gen-type-interface-decls)
mlir_tablegen(RTGISAAssemblyTypeInterfaces.cpp.inc -gen-type-interface-defs)
add_public_tablegen_target(CIRCTRTGISAAssemblyTypeInterfacesIncGen)
add_dependencies(circt-headers CIRCTRTGISAAssemblyTypeInterfacesIncGen)

mlir_tablegen(RTGISAAssemblyOpInterfaces.h.inc -gen-op-interface-decls)
mlir_tablegen(RTGISAAssemblyOpInterfaces.cpp.inc -gen-op-interface-defs)
add_public_tablegen_target(CIRCTRTGISAAssemblyOpInterfacesIncGen)
add_dependencies(circt-headers CIRCTRTGISAAssemblyOpInterfacesIncGen)

set(LLVM_TARGET_DEFINITIONS RTGAttributes.td)
mlir_tablegen(RTGAttributes.h.inc -gen-attrdef-decls)
mlir_tablegen(RTGAttributes.cpp.inc -gen-attrdef-defs)
add_public_tablegen_target(CIRCTRTGAttributeIncGen)
