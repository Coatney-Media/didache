### NX 21+

⚡ tsconfig not being generated

BROKEN: NX 21 no longer generates the tsconfig.base.json because it has shifted away from this. So the generator does not create it but the system still expects it to be there.

FIX: the fix is to create the tsconfig.base.json manually
