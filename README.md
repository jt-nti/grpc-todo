# grpc-todo

Just experimenting with gRPC

These links seemed useful along the way:

- https://grpc.io/docs/tutorials/basic/web.html
- https://medium.com/namely-labs/how-we-build-grpc-services-at-namely-52a3ae9e7c35
- https://blog.bugsnag.com/libraries-for-grpc-services/
- https://medium.com/building-ibotta/building-a-scaleable-protocol-buffers-grpc-artifact-pipeline-5265c5118c9d
- https://dzone.com/articles/packaging-generated-code-for-grpc-services

Things to investigate:

- protoc-gen-lint

```
docker run --rm                             \
  $dependency_mounts                        \ mount dependent pkgs
  -v $PACKAGE_DIR:/defs                     \ .proto files compiled
  namely/protoc-all:1.11                    \ label is gRPC version
     -i src/main/proto $dependency_includes \ node_modules includes
     -d src/main/proto                      \ location of .proto's
     -o $BUILD_PATH                         \ output location
     -l $BUILD_LANG                         \ ruby, node, python etc
     --with-docs
```
