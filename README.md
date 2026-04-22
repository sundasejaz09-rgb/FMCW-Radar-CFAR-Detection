function CFAR_map = cfar(RDM, Tr, Td, Gr, Gd, offset)

[R, D] = size(RDM);
CFAR_map = zeros(R, D);

for i = Tr+Gr+1 : R-(Tr+Gr)
    for j = Td+Gd+1 : D-(Td+Gd)
        
        noise_level = 0;
        
        for p = i-(Tr+Gr) : i+(Tr+Gr)
            for q = j-(Td+Gd) : j+(Td+Gd)
                
                if (abs(i-p) > Gr || abs(j-q) > Gd)
                    noise_level = noise_level + db2pow(RDM(p,q));
                end
                
            end
        end
        
        num_cells = ((2*(Tr+Gr)+1)*(2*(Td+Gd)+1)) - ((2*Gr+1)*(2*Gd+1));
        
        threshold = pow2db(noise_level / num_cells);
        threshold = threshold + offset;
        
        CUT = RDM(i,j);
        
        if (CUT > threshold)
            CFAR_map(i,j) = 1;
        else
            CFAR_map(i,j) = 0;
        end
        
    end
end

end
